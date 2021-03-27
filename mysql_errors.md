# MySQL Error Logs

**数据库的所有操作之前都请首先进行备份处理，避免造成二次损害**

### MySQL 启动失败（1067），错误日志：Error: could not open single-table tablespace file ./mysql/innodb_index_stats.ibd

Fix: 

1. 去掉 MySQL 配置文件中 `# innodb_force_recovery = 2` 项的注释，如果没有则添加此项。

2. 启动 MySQL，此时 MySQL 会尝试自己修复错误。

3. 修复后，将第一步的配置项注释掉。

4. 重启 MySQL。

参考：[stackoverflow.com](https://stackoverflow.com/questions/18575755/xampp-mysql-could-not-open-single-table-tablespace-file-mysql-innodb-index-st)

### 新建用户时提示 SQL Error (126): Incorrect key file for table '.\mysql\user.MYI'; try to repair it

Fix：

进入 MySQL, 执行以下命令修复表：

```sql
USE mysql;
CHECK TABLE `user`;
REPAIR TABLE `user`;
```

参考：[stackexchange.com](https://dba.stackexchange.com/questions/124956/sql-error-126-incorrect-key-file-for-table-mysql-user-myi-try-to-repair)

### 在进行大量数据删除的时候提示磁盘空间不足，执行失败（ERROR 1026: Error writing file '/path/to/some.tmp' <errno: 28 - No space left on device>）

因为在进行删除操作的时候，MySQL 会写缓存文件到磁盘，如果磁盘空间所剩没多少，就容易造成该问题。

解决方案暂列两种：

1. 加硬盘空间。

2. 修改配置文件中 `tmpdir="/your/tmpdir/"` 项，将目录修改到空间足够的分区目录（Windows 下默认会在系统盘）。
