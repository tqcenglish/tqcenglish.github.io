title: Node 错误处理
date: 2018-09-02
tags:  Node.js
---
Node 有多种错误处理方式， 异步与同步使用不同的方式捕获异常。 在写 web 框架时需要保证异常的处理不能出现内存泄漏或者因为单次请求异常导致服务终止。

- try catch, 不能处理 promise 错误
- .catch(), 处理 promise 错误

Http 服务最重要是即使一个请求导致内部错误，但是服务端不能停止。 使用

``` Node.js
 process.on('uncaughtException', (err) => {
       console.error('uncaughtException');
    });
```

保持服务器不中断, 另外可以使用 pm2 保活.

# 断言
assert 两种模式, 建议strict.