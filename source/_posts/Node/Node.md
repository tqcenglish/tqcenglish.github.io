title: Node
date: 2016-12-13 
tags: node 
---

## 常用函数

- 生成指定数量的数组
``` bash
Array.from(Array(N).keys());
```

## ES6 
- const, let 替换 var 。 var 会提升作用域, for 循环慎用.
- 模版字符串, 实现字符串格式化/字符串多行显示.
- 新加函数: includes, startsWith, endsWith, padStart, padEnd.
- 函数默认值. num = num || 2000. 实际值为 0时会出错。
- 箭头函数: 函数体内的this对象，就是定义时所在的对象，而不是使用时所在的对象.
- 
## Node.js 配置
- 代码中常用 *** process.env.NODE_ENV *** 判断当前是开发环境, 启动程序时通过如下方式配置
``` javascript
export NODE_ENV=development&& nodemon --harmony --use_strict index.js  -w
set NODE_ENV=development&& nodemon --harmony --use_strict index.js  -w
```
另外参考 [cross-env](https://github.com/kentcdodds/cross-env) 实现跨平台环境变量设置。

## Node.js 学习文档

* [Node.js 调试指南](https://github.com/nswbmw/node-in-debugging)
* [Node的艺术](https://github.com/maxogden/art-of-node/blob/master/readme.zh-cn.md)
* [An Introduction to libuv](http://nikhilm.github.io/uvbook/)
* [JavaScript Promise迷你书](http://liubin.org/promises-book/#promise-polyfill)
* [awesome-nodejs](https://github.com/sindresorhus/awesome-nodejs)
* [ECMAScript® 2015 Language Specification](http://www.ecma-international.org/ecma-262/6.0/)
* [nodejs stream 手册](https://github.com/jabez128/stream-handbook)
* [promises-book](https://github.com/azu/promises-book)
* [art-of-node](https://github.com/maxogden/art-of-node)
* [pug 中文](https://pugjs.org/zh-cn/api/getting-started.html)
* [全栈工程师培训材料](https://github.com/ruanyf/jstraining)

## ReactiveX
* [RxJava文档中文版](https://mcxiaoke.gitbooks.io/rxdocs/content/)

## ES6
* [阮一峰](http://es6.ruanyifeng.com/)

## 视频教程
* [javascript30](https://javascript30.com/)

## 软件
* [jssip-demo](https://github.com/versatica/tryit-jssip) 官方demo


## Node 编译
[Node 编译](https://github.com/nodejs/node/blob/master/BUILDING.md) 

