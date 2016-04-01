title: Kail
date: 2015-12-01 21:34:44
tags: linux
---

# Kail 安装

## ibus
kail安装后不能输入中文，需要安装ibus. 小企鹅输入法不能自由切换。

## vpn
系统没有自带pptp协议。

```bash
apt-get install network-manager-pptp
apt-get install network-manager-pptp-gnome
/etc/init.d/network-manager restart
```

## Tweak Tool
进行全局的黑暗模式设置时出现 'Error writing setting'

http://ubuntuforums.org/showthread.php?t=2230562 在config 中创建 gtk-3.0/settings.ini

## ctags
aptitude install exuberant-ctags

## except
 sudo aptitude install expect
#bin/bash
alis gvim = /usr/bin/gvim --remote-tab-silent --disable-crash-dialog "$@" 2>/dev/null
