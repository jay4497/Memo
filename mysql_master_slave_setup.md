# MySQL 主从部署配置

### 准备

* 主库 Master: 192.168.8.51

* 从库 Slave: 192.168.8.188

**注意**：主从库同步前必需保证数据已一致，主从同步开始后只会同步配置主从之后的数据。

### 主库 Master 配置

1. 创建可供从库访问主库的用户

    ```
    mysql > GRANT REPLICATION SLAVE ON *.* TO 'slave01'@'192.168.8.188' IDENTIFIED BY 'salve01password';
    mysql > FLUSH PRIVILEGES;
    ```

    REPLICATION SLAVE 权限是全局的，所以此处必须是 `*.*`，不然会报错。需要同步指定的数据库可以通过步骤 2 在主库配置文件中配置 `binlog-do-db` 项。

2. 修改主库配置文件，开启 binlog

    ```ini
    [mysqld]
    server-id=1
    log-bin=/var/log/mysql-binlog
    # binlog-do-db=db_test
    # binlog-do-db=db_user
    # binlog-ignore-db=mysql
    # binlog-ignore-db=information_schema
    # binlog-ignore-db=performance_schema
    ```

    `server-id`: 主从关系中唯一的 ID 号。

    `log-bin`: 同步日志的路径。

    `binlog-do-db`: 指定要同步的数据库名，多个的话可以重复此配置项。不指定则同步全库。

    `binlog-ignore-db`: 忽略同步的数据库名。

    **最后重启 MySQL**。

3. 查看主库当前 binlog 的名称和偏移量，记录下来供从库使用

    ```
    mysql > SHOW MASTER STATUS;
    ```

    得到结果表格中 `File` 列为日志名称，`Position` 列为偏移量。

主库配置完毕。

### 从库 Slave 配置

1. 修改从库配置文件

    ```ini
    [mysqld]
    server-id=2
    # master-host=192.168.8.51
    # master-user=slave01
    # master-password=slave01password
    # master-port=3306
    ```

    MySQL 5.5+ 版本不支持配置文件中的 master-* 类配置项，需要通过以下方式配置：

    ```
    mysql > CHANGE MASTER TO MASTER_HOST = '192.168.8.51',
            MASTER_USER = 'slave01',
            MASTER_PASSWORD = 'slave01password',
            MASTER_PORT = 3306,
            MASTER_LOG_FILE = 'mysql-binlog.000001',
            MASTER_LOG_POS = 706;
    ```

    `MASTER_LOG_FILE` 和 `MASTER_LOG_POS` 分别是从上边主库配置步骤 3 获得的日志文件名和偏移量。

    **重启 MySQL**。

2. 启动 SLAVE

    ```
    mysql > START SLAVE;
    ```

    使用 `SHOW SLAVE STATUS\G;` 查看 SLAVE 状态。`Slave_IO_Running` 和 `Slave_SQL_Running` 均为 `Yes` 则表示 SLAVE 运行正常。

3. 取消主从关系

    ```
    mysql > STOP SLAVE;
    mysql > RESET SLAVE;
    mysql > CHANGE MASTER TO MASTER_HOST = ' ';
    ```

### binlog 文件清理

**自动清理**

通过配置文件配置过期时间。

```ini
# add the following line to my.ini/my.cnf
expire_logs_days=30
```

以上示例设置表示保留 30 天内 binlog 文件。0 表示保留所有，即不清理。

**手动清理**

MySQL shell 中执行以下命令清理指定日期前的 binlog 文件。

```mysql
mysql > purge binary logs before '2019-10-01 00:00:00';
```

### 从库报错

**[1032] Could not execute Delete_rows event on table database.table_name; Can't find record in 'table_name', Error_code: 1032; handler error HA_ERR_KEY_NOT_FOUND; the event's master log mysql-bin.xxxxxx, end_log_pos xxxx**

两种解决方法，如下：

1. 尝试修改配置文件跳过指定错误。修改完成后重启服务。

    ```ini
    slave-skip-errors=1032
    ```

2. 在不重启服务的情况，设置全局参数 `slave_exec_mode` 为幂等模式(IDEMPOTENT)，默认情况下为严格模式(STRICT)。

    ```
    mysql > stop slave;
    mysql > set global slave_exec_mode='IDEMPOTENT';
    mysql > start slave;
    ```

**-- The End**
