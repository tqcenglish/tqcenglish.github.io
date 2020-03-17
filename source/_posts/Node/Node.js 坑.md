title: Node.js 坑
date: 2018-08-25
tags: javascript Node.js
---

Node 由于其入门简单，语法少广受程序猿欢迎。 但是 Node 本身的缺陷或使用者不熟悉在一下方面会出现一些意料之外的事情。

- 不用用于处理复杂任务，如果非做不可。开启多线程模式。
- https://github.com/mcollina/make-promises-safe 内存泄露。
- sails orm wterline 查询缓慢。
- koa sttic 中间件浏览器访问不显示目录，实际能正常读取(缺少 index.html)。