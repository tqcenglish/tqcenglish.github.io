title: DNS
date: 2018-09–02
tags: 
---

# DNS
* DNS是一个全球分布式数据库
* 操作系统先查询/etc/hosts/， 然后去DNS查询
* 操作系统提供一个方法为名称服务器(DNS服务器)指定IP地址  /etc/resolv.conf
* Python定义socket.getaddrinfo()返回一个tuple的list, 根据所支持的不同协议产生一个结果
	host is a simple utility for performing DNS lookups 对于一个IP地址，完全可能不存在反向的映射。反向查找时需要捕获socket.herror()异常,反向查询存在欺骗，由于ＤＮＳ信息的授权方式，反向查询的授权是基于ＩＰ地址的.先反向再正向，确定结果
