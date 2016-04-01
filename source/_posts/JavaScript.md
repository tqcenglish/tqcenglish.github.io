title: JavaScript
date: 2015-12-01 21:34:44
tags: node.js,
---

# npm ^ ~ 的区别
In the simplest terms, the tilde matches the most recent minor version (the middle number). ~1.2.3 will match all 1.2.x versions but will miss 1.3.0.

The caret, on the other hand, is more relaxed. It will update you to the most recent minor version or patch version (the second or third number). ^1.2.3 will match any 1.x.x release including 1.3.0, but will hold off on 2.0.0.

# brew 用法

brew的使用方法
Homebrew的可执行命令是brew，其基本使用方法如下（以wget为例）。
查找软件包
brew search wget
安装软件包
brew install wget
列出已安装的软件包
brew list
删除软件包
brew remove wget
查看软件包信息
brew info wget
列出软件包的依赖关系
brew deps wget
更新brew
brew update
列出过时的软件包（已安装但不是最新版本）
brew outdated
更新过时的软件包（全部或指定）
brew upgrade
或
brew upgrade wget


<div class="dataTable_wrapper">
                        <table datatable="ng" class="table table-striped table-bordered table-hover"
                               id="dataTables-example">
                            <thead>
                            <tr>
                                <th>客户名</th>
                                <th>坐席名</th>
                                <th>呼入/呼出</th>
                                <th>留言时长</th>
                                <th>操作</th>
                            </tr>
                            </thead>
                            <tbody>
                            <!--
                            <tr class="odd gradeX" ng-repeat="file in value">
                                <td>{{ file.from }}</td>
                                <td>{{ dir }}</td>
                                <td>{{ file.date }}-{{ file.time }}</td>
                                <td>{{ file.time }}</td>
                                <td>
                                    <div class="center btn-group" role="group" aria-label="...">
                                        <button type="button" class="btn btn-Primary" data-toggle="modal"
                                                data-target="#edit_recording_modal"
                                                ng-mouseup="playRecording(dir,file.fileName)">
                                            Play
                                        </button>
                                        <button type="button" class="btn btn-danger"
                                                ng-mouseup="deleteRecording(dir,file.fileName)">
                                            Delete
                                        </button>
                                    </div>
                                </td>
                            </tr>
                            -->
                            </tbody>
                        </table>
                    </div>
# 对w3school中的javascriipt部分进行理解和笔记
- document.write("这会覆盖文档")， 文档加载后再调用(例如函数中)这个函数会覆盖所有显示。
- alert函数用于DEBUG
- <script>标签中不需要再添加type='text/javascript'因为现代浏览器和html5都是以javascript为默认脚步语言。
- <script>放在<head>或<body>中。
- 必须以字母或$,_开头。大小写敏感。
- 重新声明不会导致变量的直消失

``` javascript
  //变量的直依然是 Volvo
  var carname="Volvo"
  var carname;
```
- 通过null清空变量
- 全局变量在页面关闭后删除，局部变量在函数运行后删除。

- 创建对象两种方法. 直接定义或函数定义

``` javascript
  - new Object()
  - fuction object(){
    this.
  }
```

- javascript基于原型(prototype)不基于类。
- 字符串对象方法
``` javascript
  //计算字符串长度
  length()
  //将字符串转化为大写
  toUpperCase()
  //定位字符串在指定字符串中首次出现的位置
  indexOf()
  //match/replace

```

#JavaScript资源
##[es6-in-depth](https://hacks.mozilla.org/category/es6-in-depth/)
1. [ES6简介](http://www.csdn.net/article/2015-06-15/2824955-es6-in-depth-an-introduction)
2. [迭代器和for-of循环](http://www.csdn.net/article/2015-06-15/2824965-es6-in-depth-iterators-and-the-for-of-loop)
3. [生成器](http://www.csdn.net/article/2015-06-15/2824967-es6-in-depth-generators)
4. [模版字符串](http://www.csdn.net/article/2015-06-24/2825037-es6-in-depth-template-strings-2)
5. [剩余参数和默认参数](http://www.csdn.net/article/2015-06-29/2825075-es6-in-depth-rest-parameters-and-defaults)
6. [解构赋值](http://www.csdn.net/article/2015-07-07/2825149-es6-in-depth-destructuring)
7. [箭头函数](http://www.csdn.net/article/2015-07-08/2825159-es6-in-depth-arrow-functions)
8. [JS的第七种基本类型Symbols](http://www.csdn.net/article/2015-07-09/2825172-es6-in-depth-symbols)
9. [使用Babel和Broccoli](http://www.csdn.net/article/2015-07-22/2825271-es6-in-depth-babel-and-broccoli)
10. [更深入了解生成器](http://www.csdn.net/article/2015-08-13/2825452-es6-in-depth-generators-continued)

for-in语法是被设计来遍历普通的“键值对”对象的，不适合用在数组上

* js 多点触控插件  http://hammerjs.github.io/


#关于JavaScript测试汇总
##[karma](https://github.com/karma-runner/karma)
* [http://karma-runner.github.io](http://karma-runner.github.io)
##[mocha](http://mochajs.org/)
* [mocha github](https://github.com/mochajs/mocha)
##[jasmine](http://jasmine.github.io/)
Jasmine 是一个简易的JS单元测试框架。Jasmine 不依赖于任何浏览器、DOM、或者是任何 JavaScript 而存在。它适用于所有网站、Node.js 项目，或者是任何能够在 JavaScript 上面运行的程序。

* [jasmine github](https://github.com/jasmine/jasmine)
* [jasmine node](http://jasmine.github.io/edge/node.html)
* [JavaScript 单元测试框架：Jasmine 初探](http://www.ibm.com/developerworks/cn/web/1404_changwz_jasmine]
* [JavaScript单元测试框架-Jasmine](http://www.cnblogs.com/zhcncn/p/4330112.html)
##istanbul
istanbul 是一个 JavaScript 的代码覆盖率检查工具。

* [istanbul github](https://github.com/gotwarlost/istanbul)

##[requirejs](http://requirejs.org/)
##[phantomjs](http://phantomjs.org/)
PhantomJS is a headless WebKit scriptable with a JavaScript API. It has fast and native support for various web standards: DOM handling, CSS selector, JSON, Canvas, and SVG

##[underscore](https://github.com/jashkenas/underscore)
JavaScript's utility _ belt [http://underscorejs.org](http://underscorejs.org)

##[bower]
* [bower api](http://bower.io/docs/api/)

##[supertest]()
Super-agent driven library for testing node.js HTTP servers using a fluent API


# 一些 JavaScript 项目

## [togetherjs](https://togetherjs.com/) mozilla
用于共享屏幕，协同工作。可以发送消息与基于webRTC的对讲。

* ［github地址](https://github.com/mozilla/togetherjs)


# 相关组织在Github上地址

* [mozila](https://github.com/mozilla)
