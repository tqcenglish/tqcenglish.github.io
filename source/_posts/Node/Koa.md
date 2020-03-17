title: Koa
date: 2018-09-04
tags: Node
---

Koa 是一个小型，易扩展的 web 框架。 由于源码很少，是一个很好的 web 框架源码研究项目。

- [koa](https://github.com/koajs/koa)
- [koa express 比较](https://github.com/demopark/koa-docs-Zh-CN/blob/master/koa-vs-express.md)
- [koa 相关框架与中间件](https://github.com/koajs/koa/wiki)
- [中文文档](https://github.com/demopark/koa-docs-Zh-CN)
- [koa 阮一峰](http://www.ruanyifeng.com/blog/2017/08/koa.html)

## Koa 引用的包
Koa 本身源代码极少, 可以通过依赖的包了解一个 web 服务器需要考虑的细节. 另外 koa 将常用 http 功能以 koa-* 的方式分割成中间件。

- [only](https://github.com/tj/node-only) 将一个对象下划线开始的属性理解为私有，不暴露外部。 类似 loadh 中的 _.pickup
- [on-finished](https://github.com/jshttp/on-finished) http req/res 结束时执行。 类似 go defer 关键字。
- [statuses](https://github.com/jshttp/statuses) http 响应状态码规范化。
- [depd](https://github.com/dougwilson/nodejs-depd) 打印废弃通知(提示用户 api 变动)
- [delegates](https://github.com/tj/node-delegates) 原型修改. 将 req/res 方法绑定到 context.
- [cookies](https://github.com/pillarjs/cookies) 获取/设置 cookie
- [accepts](https://github.com/jshttp/accepts) http 响应类型

## 其他

- 定义函数名对调试和日志更友善
- koa-compose 用于合并多个中间件
- DEBUG=koa*  开启调试
- 错误处理 try-catch -> app.on(‘error’) ->app.onerror