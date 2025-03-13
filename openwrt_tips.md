# OpenWrt 备忘

使用的镜像 kwrt.tar.gz 来自 [openwrt.ai](https://openwrt.ai)，下载列表有针对 LXC 和 Docker 的镜像包

### PVE LXC 方式创建

```shell
# 上传镜像包 kwrt.tar.gz 到根节点（local）的 CT 模板
# 创建 ID 为 100、硬盘为 8G、内存 2G、双核 CPU 的虚拟机
pct create 100 local:vztmpl/kwrt.tar.gz --rootfs local:8 --ostype unmanaged --hostname OpenWrt --arch amd64 --cores 2 --memory 2048 --swap 1024 --onboot yes -net0 bridge=vmbr0,name=eth0
# 通过硬盘 UUID 挂载硬盘到虚拟机的 /mnt/download 目录，使用 blkid /dev/sdb 可以获取硬盘（/dev/sdb）的 UUID
pct set 100 -mp0 /dev/disk/by-uuid/disk-uuid-example,mp=/mnt/download
```

### Docker 方式创建

```shell
# 创建网络
ip link set enp3s0 promisc on
docker network create -d macvlan --subnet=192.168.1.0/24 --gateway=192.168.1.1 -o parent=enp3s0 openwrt_net
# 导入本地镜像
docker import /path/to/kwrt.tar.gz openwrt/kwrt
# 启动容器
docker run --restart always --name openwrt -d --network openwrt_net --privileged --ip 192.168.1.255 openwrt/kwrt /sbin/init
```
