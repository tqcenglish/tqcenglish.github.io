title: Linux
date: 2015-12-01 21:34:44
tags: linux
---
##Linux命令
### lsof

List Opened Files
*   [lsof常被使用的功能选项](http://www.dutor.net/index.php/2012/03/lsof/)
*   [wiki](http://en.wikipedia.org/wiki/Lsof)
### ufw

在redhat中关闭防火墙:
```shell
    service iptables stop
```
但是ubuntu下使用Uncomplicated Fire Wall(UFW)的防火墙，这实际上是一个 iptable 的管理工具。
```shell
    sudo ufw enable             开启了防火墙，并在系统启动时自动开启
    sudo ufw default deny       关闭所有外部对本机的访问
```
### uname

*	uname --help
*   	Usage: uname [OPTION]...
*   	Print certain system information.  With no OPTION, same as -s
### uptime

显示开机的时间和用户数
### hostname

设置主机名或NIS
### man

man hier 描述文件系统的层次结构
### last

 last reboot 显示系统reboot历史记录
### dmesg

 显示开机信息
### watch

 监测一个命令的运行结果

### netstat

 netstat可以显示传输层协议(TCP/UDP)和ICMP之间的网络包相关信息.

~~~{.sh}

    netstat -s | less 	显示TCP，ICMP和UDP活动概况
    netstat -tanp  		查看活跃的tcp连接
    netstat -uanp		查看活跃的udp连接
    netstat -tanp | grep -i listen 		查看监听端口的守护进程
~~~

### nmap
网络探测和扫描工具

nmap - Network exploration tool and security / port scanner

~~~{.sh}

    nmap 	127.0.0.1	扫描127.0.0.1的计算机各个端口
    nmap 	127.0.0.1/24	扫描整个网络的主机
    nmap	-P0 -O -p 100-200 127.0.0.1 不使用Ping的方式扫描端口100-200,并获取被扫描系统的OS信息.
~~~

### traceroute
跟踪到主机的路由

~~~{.sh}

    traceroute www.baidu.com	默认使用UDP包, -I ICMP包, -T TCP包
    traceroute -p 25 www.baidu.com		连接25端口
~~~

### ARP 地址解析协议
arp命令获取MAC层信息,相似命令 ip neigh

~~~{.sh}

    arp -v		按照主机名显示ARP缓存条目
    arp -vn		按照Ip地址显示缓存条目
    arp -d 192.168.1.1 	删除缓存地址192.168.1.1
    arp -s 192.168.1.1	ec:6c:9f:0d:ef:65 	添加静态ARP条目

~~~

arping查询子网中IP是否使用, 找到IP设备的MAC地址.

~~~{.sh}

    arping 192.168.1.1  判断192.168.1.1是否使用, -I eth0 指定网口， -f 收到一次即停止, -c 2 查询2次
~~~

### Ping

~~~{.sh}
    ping -a 192.168.1.1 	发出声音
    ping -c 4 192.168.1.1	4次后退出
    ping -q -c 4 192.168.1.1	只显示结果
    ping -f 192.168.1.1		发送大量的包
    ping -i	3 192.168.1.1		3秒发送一个包
    ping -I eth0 192.168.1.1	指定网口
    ping -r 127.0.0.1 192.168.1.1	始发端127.0.0.1
    ping -s 1500 192.168.1.1	设置包大小1500字节， 默认56字节, 可以判断连接是否正常和网卡是否正常

~~~

### dig
从DNS服务器查询信息

~~~{.sh}

    dig	localhost		先查询/etc/resolv.conf然后查找服务器
    dig	localhost @8.8.8.8	指定DNS服务器8.8.8.8
    dig  +trace www.baidu.com	递归跟踪DNS服务器
    dig  +short www.baidu.com	只显示名字/Ip地址对
    dig  -x 8.8.8.8			反向查询

~~~

### host
host实现DNS反向查询, hostname获取本机主机名信息.

~~~{.sh}

    hostname	主机名全称 -s 简称  -d	域名
~~~

### ethtool
查询网卡驱动信息和设置网卡

~~~{.sh}

    ethtool -i eth0		查看驱动信息
    ethtool -S eth0		查看统计信息
    ethtool -s eth0	speed 100 duplex full autoneg off 关闭自动协商,固定100Mbpx和全双工模式.
~~~
