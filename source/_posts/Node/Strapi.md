title: Strapi
date: 2018-09-02
tags:  Node.js
---

自 2015 年开始从 Java (Android) 转 Web(Node.js 前后端), 第一次使用 MVC 框架 Sails。 到现在了解使用 Strapi.

Sails 是一个全面的 MVC 框架。 在那个时候(2015) 高居 Github 关注前列。 由于缺少经验的原因. Sails 使用中出现如下问题

- ORM 效率低， Waterline 虽然使用方便，但是使用简单的 count 会读取所有数据到内存。 这是完全不能接受。
- 内存泄漏, 由于其他原因整个项目是运行在类似树莓派的嵌入式环境下。 当多用户登录会导致内存居高不下。

为什么又要了解 Strapi 一个与 Sails 类似的框架。

- loopback IBM 推动, 细节更多。 loopback4 完全使用 Spring 注解方式(不喜欢)。
- egg 基于 KOA, 比 KOA 更全面的 WEB 框架。 至少不需要找那么多中间件。
- fastify 直接基于 Node.js. 在 json 序列化和 路由查询方便有特别的优化。 

上面的框架都很好，但是我需要一个前端更灵活的。 上面框架使用 ant-pro 可以写出高效的 admin 后台。 但是 strapi 有他独特的方式。 我没有使用过老版本直接使用新版本 3.0

- 插件化， 前后端插件化。
- CRUD 自动生成, 支持分页/查询/过滤。

strapi 模块化，基本界面在 admin 目录， 通过 nam run build 打包。 插件界面在对应目录下， 也需要 nam run build 。

