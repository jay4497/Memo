# ElasticSearch Tips

**注意**：实际使用中，以下所有示例配置文件中 # 注释部分要全部删除，因为这并不是 Logstash 配置文件的标准注释

### 查询设置分词间相隔最高间隔

通过设置 `slop` 为 0 实现类似 MySQL 中的 `LIKE` 查询 (LIKE '%keyword%')。

```JSON
{
  "query": {
    "match_phrase": {
      "market": {
        "query": "科技",
        "slop": 0
      }
    }
  }
}
```

### 使用 Logstash 同步 MySQL 数据

需要借助 **logstash-input-jdbc** 插件。本示例使用的 Logstash 7.2 版本本身自带，没有的需要自行安装一下。

```
# file: mysql_sync.conf
input {
  jdbc {
    # 配置 JDBC 的路径，MySQL 版本不同会需要不同版本的 JDBC
    jdbc_driver_library => "/path/to/mysql-connector-java-5.1.46.jar"
    jdbc_driver_class => "com.mysql.jdbc.Driver"
    # MySQL 连接
    jdbc_connection_string => "jdbc:mysql://host:3306/database_name?serverTimezone=GMT%2B8&zeroDateTimeBehavior=convertToNull"
    jdbc_user => "database_user"
    jdbc_password => "secret"
    jdbc_paging_enabled => true
    jdbc_page_size => 50000
    jdbc_fetch_size => 10000
    connection_retry_attempts => 3
    connection_retry_attempts_wait_time => 2
    jdbc_pool_timeout => 5
    lowercase_column_names => true
    # 是否记录最后运行相关信息，用于增量同步
    record_last_run => true
    # 最后运行信息记录保存路径，不设置则默认保存在用户根目录下
    last_run_metadata_path => "/path/to/.my_last_run"
    # 定时规则，同 cron 规则
    schedule => "* * * * *"
    use_column_value => true
    # 跟踪字段，设置了 record_last_run 的话就会记录下该字段值
    tracking_column => "id"
    # 读取要同步的数据记录，变量 sql_last_value 会取 record_last_run 记录的值
    statement => "SELECT * FROM table_name WHERE id > :sql_last_value"
  }
}

output {
  elasticsearch {
    # ES 服务地址
    hosts => ["localhost:9200"]
    # ES 索引名称
    index => "index_name"
    # 文档 id 使用 MySQL 表中的 id
    document_id => "%{id}"
  }
}

# 运行
/path/to/bin/logstash -f /path/to/mysql_sync.conf
```

### 使用 Logstash 导入 Nginx 日志

```
# file: access_logs.conf
input { 
  file {
    # 文件路径，可以是数组，读取多个文件，如 path => ["/path/to/site1.log", "/path/to/site2.log"]，也可以使用通配符，如 path => "/path/to/*.log"
    path => "/path/to/your_site.access.log"
    start_position => "beginning"
    # 文件 inode 记录，会记录文件读取记录的最后位置，如果存在此文件，会忽略 start_position 设置，强行从已记录的位置开始读取数据
    sincedb_path => "/path/to/.sincedb"
    # 每隔多少秒写一次 sincedb 文件，默认为 15s
    sincedb_write_interval => 10
    # 每隔多少秒检查一次被监听文件的状态（是否有更新），默认为 1s
    stat_interval => 2
  }
}

filter {
  grok {
    match => {"message" => "%{COMBINEDAPACHELOG}"}
  }
  date {
    match => ["timestamp" , "yyyy/dd/MMM HH:mm:ss"]
  }
}

output {
  elasticsearch { 
    hosts => ["localhost:9200"]
    index => "access_logs"
  }
}

# 运行
/path/to/bin/logstash -f /path/to/access_logs.conf
```

### 当文档字段类型初始设置不符合需求又不方便或不能更改原字段类型的时候，可以使用 runtime 字段来补救

```
# Method
PUT http://host:9200/your_doc/_mappings
# Request body 这里设置一个将原字段值转换为 double 类型的 runtime 字段
{
    "runtime": {
      "your_runtime_field_name": {
        "type": "double",
        "script": {
          "source": "emit(Double.parseDouble(doc['your_original_field'].value))"
        }
      }
    }
}
```

其中 `script.source` 段使用的是一段 `painless` 脚本，语言参考 [painless scripting language](https://www.elastic.co/guide/en/elasticsearch/painless/current/index.html)。
