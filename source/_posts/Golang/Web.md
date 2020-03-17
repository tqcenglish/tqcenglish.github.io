title: golang 库
date: 2016-12-14 
tags: golang
---
Go 语言自带 http 库本身已是很高效，当前 web 库主要分完整的框架或路由库两种。若希望后期完全可控选库可能更好。

# 框架
- Web 框架 gin, golang 在微服务/web 开发都有很多选择。 我选择 gin 因为它功能够全。 当然其他框架也有不同的优势。

# 软件库
* [xorm.io](https://github.com/go-xorm/xorm) Simple and Powerful ORM for Go, support mysql,postgres,tidb,sqlite3,mssql,oracle。 关系数据库 ORM， 现在 WEB 纯手写 SQL 很少了吧。

* [captcha](https://github.com/go-macaron/captcha) macaron 验证码中间件(不适用于 gin)