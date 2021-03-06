# Linux 入门/运维

### Linux查看进程运行的完整路径方法

通过 `ps` 及 `top` 命令查看进程信息时，只能查到相对路径，查不到的进程的详细信息，如绝对路径等。

这时，我们可以通过以下方法来查看进程的详细信息：

Linux 在启动一个进程时，系统会在 `/proc` 下创建一个以 `PID` 命名的文件夹，在该文件夹下会有我们的进程的信息。

其中包括一个名为 `exe` 的文件即记录了绝对路径，通过 `ls –l` 命令即可查看，以下 `PID` 只是代指，实际操作请替换为要查看的进程的 `PID` 数。

```bash
ls -l /proc/PID
```

`cwd` 符号链接的是进程运行目录

`exe` 符号链接的就是执行程序的绝对路径

`cmdline` 就是程序运行时输入的命令行命令

`environ` 记录了进程运行时的环境变量

`fd` 目录下是进程打开或使用的文件的符号链接

### CentOS 初始任务脚本

```crontab
# 定时更新本机时间到网络标准时间(每天)
0 0 * * * /usr/sbin/ntpdate -u ntp.api.bz

# 保持系统更新(每七天)
0 1 */7 * * /usr/bin/yum update -y -q
```

### 使用 SSH KEY 远程登录

1. 本地生成 SSH 私钥及公钥。Windows 下可借助 **Git Bash** 来生成。

	```
	ssh-keygen -t rsa
	```

2. 命令会提示生成的密钥保存的路径，记住该路径保证下一步能找到生成的公钥。

3. 将生成的公钥的内容添加到远程服务器的 `~/.ssh/authorized_keys` 中，如没有此文件，需新建。

4. 重启远程服务器的 SSH 服务，完成。
