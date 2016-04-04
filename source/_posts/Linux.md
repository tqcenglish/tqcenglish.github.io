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

#### getopts
处理命令行参数

    getopts options variable
getopts 的设计目标是在循环中运行,每次执行循环，getopts 就检查下一个命令行参数,并判断它是否合法。

即检查参数是否以 - 开头，后面跟一个包含在 options 中的字母.如果是,就把匹配的选项字母存在指定的变量 variable 中,并返回退出状态0;如果 - 后面的字母没有包含在 options 中,就在 variable 中存入一个 ?,并返回退出状态0;如果命令行中已经没有参数,或者下一个参数不以 - 开头，就返回不为0的退出状态。

  1. getopts 允许把选项堆叠在一起（如 -ms）
  2. 如要带参数,须在对应选项后加:(如h后需加参数 h:ms),此时选项和参数之间至少有一个空白字符分隔,这样的选项不能堆叠。
  3. 如果在需要参数的选项之后没有找到参数,它就在给定的变量中存入?,并向标准错误中写入错误消息.否则将实际参数写入特殊变量: OPTARG
  4. 另外一个特殊变量: OPTIND,反映下一个要处理的参数索引,初值是1,每次执行 getopts 时都会更新.

  [例子](http://www.cnblogs.com/xiangzi888/archive/2012/04/03/2430736.html)

#### bc
计算器

  * ibase用于设置输入数据的进制
  * obase用于输出的数据进制

下面将4按照2进制输出100

    echo "obase=2;4" | bc

#### seq
seq -- print sequences of numbers


#软件
新系统需要的软件。
##meld
文件夹对比工具

##sysv-rc-conf
修改服务管理程序

## 右键开启终端
sudo apt-get install nautilus-open-terminal

# 下载工具
sudo apt-get install aria2

# mysql

sudo apt-get install mysql-server-5.6

#php

sudo apt-get install php5
sudo aptitude  install php5-mysql

#f.lux
sudo add-apt-repository ppa:kilian/f.lux
sudo apt-get update
sudo apt-get install fluxgui

# zsh
sudo aptitude install zsh
https://github.com/robbyrussell/oh-my-zsh

# android
sudo apt-get install lib32stdc++6
sudo apt-get install zlib1g:i386
sudo apt-get install lib32z1

# vim
sudo aptitude install vim
sudo aptitude installl vim-gnome

# 鼠标自然滚动

~~~bash
sudo add-apt-repository ppa:zedtux/naturalscrolling
sudo apt-get update
sudo apt-get install naturalscrolling
~~~
