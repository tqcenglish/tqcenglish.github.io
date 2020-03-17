title: 软件
date: 2016-04-06
tags: soft
---
一些有用的开源软件和工具。 
- 自建服务类型，在自己 vps 上运行。
- 工具类型，参考实现二次开发。

# [Mailtrain](https://mailtrain.org/) [源码](https://github.com/andris9/mailtrain)
基于 Express 实现群发邮件管理工具。 能上传 csv， 自定义字段。

# [cockpit](https://cockpit-project.org/)
Red-hat开源 linux 系统状态监控。 用到的技术 C + react。 界面模块化开发，使用了 red-hat 自己的 ui 框架。


# Caddy 与 nginx 一样，作反向代理服务器. 配置更简单.

## 不同请求域名代理到内部不同端口.
一台 vps 需要运行多个 web 服务，都想使用 80/443 端口，如何处理 ? 使用 caddy 代理所有请求， 然后通过访问的二级域名判断需要代理到内部的具体端口. 

```
rewrite {
   if_op or
   if {>Referer} has /deluge
   if {>Referer} has mydomain.com/themes/css/
   if {>Referer} has mydomain.com/css/
   to /deluge/{path}
}
   
proxy /deluge http://127.0.0.1:8112 {
   without /deluge   
      transparent
      header_upstream X-Forwarded-Host {host}
}
```

[Reverse Proxy with Caddy Server](https://forum.deluge-torrent.org/viewtopic.php?t=54135)