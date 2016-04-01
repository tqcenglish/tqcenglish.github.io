title: Angular
date: 2015-12-02 09:53:51
tags: mvvm, mvc, angular
---

# Angular
Angular 包括 1.x , 2.x 两个版本。其中 1.x 为原生JS, 2.x 通过 TypeJs 转换产生.

## 1.x 与 2.x 对比

* 源码语言发生改变
* 绑定方式发生改变

# 1.x 文档
https://docs.angularjs.org/guide

#Angularjs 1.x 学习
#Angular学习链接
##phone-cat
这是一个官方的客户端实现购物车的功能，可以了解到页面的布局，页面跳转等知识。
* [phone-cat](https://docs.angularjs.org/tutorial)的官方例子。
* [phone-cat](http://www.ituring.com.cn/minibook/303)中文翻译.*部分内容过时*
* Jasmine行为驱动开发（BBD）框架

#Angularjs 2.x 学习
angular2 与第一版本差别大，并且使用了非原生的js开发。需要等项目有一定成熟度后再使用。
##相关链接
* [angular 2.0 官网](https://angular.io/)
* [angular 2.0 5 分钟](https://angular.io/docs/js/latest/quickstart.html)
* [ECMAScript 6入门](http://es6.ruanyifeng.com/)
* [ES6转ES5](https://github.com/google/traceur-compiler)
* [traceur在线转换](http://google.github.io/traceur-compiler/demo/repl.html#)
* [babeljs 另一种转换工具](https://babeljs.io/)


# [Angularjs 代码风格](https://github.com/johnpapa/angular-styleguide)
* [中文](https://github.com/johnpapa/angular-styleguide/blob/master/i18n/zh-CN.md)

## 相关Angular 项目
[angular-ui](https://angular-ui.github.io/) 对angular 的相关模块进行增强。[Github 地址](https://github.com/angular-ui)
[angular-translate](https://github.com/angular-translate) [Github地址](https://github.com/angular-translate)

##＃ [angular-translate](https://angular-translate.github.io/)
Angularjs 的国际化模块。

### [ui-router](https://github.com/angular-ui/ui-router)
比自带ng-route耿具有灵活性的路由。

### [AngularJS-Atom](https://github.com/angular-ui/AngularJS-Atom)
Atom 下的 angular 插件.

### [Angularjs bootstrap](https://angular-ui.github.io/bootstrap/)
将bootstrap的控件封装为指令, 快速开发时可以考虑，但后期修改会有限制。

* Accordion 类似风琴(侧边栏菜单)效果。
* Alert 从静态或动态数据产生警告。
* Buttons 对按钮进行分组，产生多选或单选框。
* Carousel 产生多张图片滚动效果。
* Collapse 对div的显示与消失产生动画效果。
* Datepicker 日期选择器。
* Dropdown 点击出现下拉菜单。
* Modal 服务，创建 Modal 窗口。
* Pagination 分页指令。
* Popover 在点击处弹出更过信息。
* Progressbar 进度条。
* Rating 显示可视的评价条。
* Tabs
* Timepicker 时间选择器
* Tooltip 对输入框显示 tip
* Typeahead 类似 ui-select

## Angularjs 加载优化
由于Angularjs主要做单页应用，相对普通页面需要加载更多的js。 优化需要从文件大小，是否加载方面考虑。

* 使用懒加载
* 使用 .min.js 和 .min.css

## Jquery 与 Angularjs
* http://stackoverflow.com/questions/14994391/thinking-in-angularjs-if-i-have-a-jquery-background

## [Angular规范](https://github.com/johnpapa/angular-styleguide/blob/master/i18n/zh-CN.md)

* 依赖、controller和factory 分成多个文件. **但对于 services 是否也需要呢? 限制 在services 中缓存了数据。必要吗？**
* IIFE语法 **让代码不简洁，对测试有影响**
* 模块命名需要统一规范，防止冲突。
* 引入模块是不要引入不必有的变量，多用链式语法。
* 区分模块的创建与获取。
* 回调函数用命名代替匿名函数。易读，容易调试，减少潜逃。**程序员最大的问题就是命名！！！**
* 多使用 controllerAs **没有直接使用那么方便。**
* 置顶绑定成员 与回调函数使用命名函数规则类似。
* 函数声明隐藏实现细节 同上
* 一个view对应一个controller, services可以通用
* 规划路由,**Angular UI**
