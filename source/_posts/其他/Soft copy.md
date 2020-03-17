title: Statsd
date: 2016-11-5 
tags: 监控
---

[StatsD](https://github.com/etsy/statsd) 是一个简单的网络守护进程，基于 Node.js 平台，通过 UDP 或者 TCP 方式侦听各种统计信息，包括计数器和定时器，并发送聚合信息到后端服务，例如  Graphite。

## 引用
* http://www.oschina.net/p/statsd
* http://www.oschina.net/p/graphite
* http://blogs.asterisk.org/2016/02/03/integrating-asterisk-with-statsd/ asterisk 与 statsd 集成

##
记录开源聊天软件
* https://github.com/sdelements/lets-chat
* https://github.com/mattermost/platform
* https://github.com/RocketChat/Rocket.Chat mateor 

# 链接
* https://www.oschina.net/question/2012764_2141029




gogs 是类似于 github 的自建 git 服务器. 是一款开源自建的  git 服务端，你可以将他认为是一个 mini 版本的 github.

## 安装

1.[安装文档](https://gogs.io/docs/installation)
2. 默认配置文件包含在 二进制软件包中， 直接运行会生成自定义配置文件。 若配置需要修改可以直接修改配置文件 **conf/app.ini**。

## 使用
1. 确定项目属于组织和用户， 后期就不会有修改 url 的困扰。



shadowsocks 是一个安全的 socks5 代理。

* [ss-panel](https://github.com/orvice/ss-panel) php 实现的 web 界面管理
* [shadowsocks-panel](https://github.com/sendya/shadowsocks-panel) 同上
* [shadowsocks-go mu](https://github.com/orvice/shadowsocks-go) 带多个用户管理的客户端
* [shadowsocks-go](https://github.com/shadowsocks/shadowsocks-go) go 服务端


[iterm2](http://www.iterm2.com/) MacOS 更好使用的终端

* 选中: 双击选中，三击选中整行，四击智能选中。
* ⌘ 键: 按住时同时点击文件夹或文件可以打开文件或文件夹。
* 分屏和切换。
* 自动补全和查看历史。

[iterm2 使用](http://wulfric.me/2015/08/iterm2/)



> tmux is a terminal multiplexer
> Tmux 是一个工具，用于在一个终端窗口中运行多个终端会话。

[Tmux](http://tmux.github.io/)
====

会话
----

一个 Tmux 会话中可以包含多个窗口.

``` shell
tmux new -s <name-of-my-session> // 创建第一个会话
Ctrl-b : && new -s <name-of-my-session> // 创建新会话
Ctrl-b s // 切换会话,列出所有会话
tmux attach -t test //进入名为test的session
C-b d // detach当前session(可以认为后台运行)
```

其他快捷键
====

Window操作

  C-b c 创建一个新窗口
  C-b & 关闭当前窗口
  C-b w 列出所有的窗口选择
  C-b p 切换到上一个窗口
  C-b n 切换到下一个窗口
  C-b 窗口号 使用窗口号切换窗口(例如窗口号为1的, 则C-b 1)
  C-b , 重命名当前窗口，便于识别各个窗口

Pane操作

  C-b % 横向分Terminal
  C-b " 纵向分Terminal
  C-b 方向键 则会在自由选择各面板
  C-b x 关闭当前pane
  C-b q 显示面板编号

链接

/odoo/TODO.md

===

* http://blog.jobbole.com/87584/
* http://www.linuxidc.com/Linux/2015-07/119843.html
* https://github.com/gpakosz/.tmux //   
