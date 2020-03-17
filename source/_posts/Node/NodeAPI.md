title: Node.js API
date: 2018-04-21
---

Node API 提供了网络编程，文件读取等。 通过 API 才能将 Node 用于实际业务开发中。 本文记录常使用的 API.

==

[API](http://nodejs.cn/api/) Nodejs 中文 api

逐行读取文件
==

交换模式下 一旦你开启了这个模块，node 程序将不会终止，直到你关闭接口

```javascript
  const rl = readline.createInterface({
    input: fs.createReadStream('demo.txt')
  })
  rl.on('line', async(line) =>{
    console.log(line)
  })
  rl.on('close', async()=>{
    console.log('end')
  })
```

- [Node.js Buffer与JavaScript TypeArray类型数组的异同](https://itbilu.com/nodejs/core/NyIjmp0wZ.html)