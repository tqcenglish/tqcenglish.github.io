title: raspberry
date: 2016-02-20 01:00:33
tags: linux
---

# 树莓派

# 关于SD要求
树莓派的系统主要包含两类，官方和第三方。 镜像文件一般都需要4g及以上。

* [minibianpi](https://minibianpi.wordpress.com/) 大约800M左右大小，在2g内存卡上成功。

# 关于写启动盘

通过 dd 命令写后出现 act 绿灯长亮，说明系统盘未活动，即启动失败。可能原因是 **不要设置bs参数**，另外也可能是读卡器或内存卡不兼容。 写入前需要格式化内存卡。

# 账户
 pi@raspberry

 * 账户 pi
 * 密码 raspberry

开启root账户需要先设置密码，然后解锁root账户。
 sudo passwd root
 sudo paddwd --unlock root

# Node.js
编译新版本Node.js 对GCC有要求。
