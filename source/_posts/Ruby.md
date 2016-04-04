---
layout: post
title:  "Ruby"
date:   2015-01-25
categories: 语言
---

##Ruby 篇一
基本教程[文档 - Ruby 官方网站](https://www.ruby-lang.org/zh_cn/documentation/)
[Ruby2.2 api](http://www.ruby-doc.org/core-2.2.0/)
###[花20分钟体验](https://www.ruby-lang.org/zh_cn/documentation/quickstart/)
不错的介绍 Ruby 基础知识的教程。从开始到结束不超过20分钟。


*  ** 是”次方”的意思。Math.sqrt() 开根号
*  .instance_methods 对象包含的所有的函数
*  if __FILE__ == $0 运行脚本于启动脚本比较
###七周七语言-Ruby
*  if 与 unless 关键字
*  if和unless可以使用块形式或单行形式, while 和 until也可以。
*  nil和false以外都代表true, 0也是true.
*  使用and(&&)或or(||)进行短路求值。也可以使用&和|进行正常求值。
*  鸭子模型
*
##Java对比
###Java与Ruby的相似...

*  垃圾收集管理为你管理内存。
*  对象是强类型。
*  有公共，私有和保护的方法。
*  有嵌入的文档工具（Ruby的工具叫RDoc的）。通过RDOC产生的文档看起来与通过javadoc产生的非常相似。
差异

###Java和Ruby差别...

*  你不需要编译代码。您只需直接运行它。
*  有几种不同的流行的第三方GUI工具包。Ruby的 ​​用户可以尝试WxRuby ， FXRuby ， Ruby GNOME2 ， Qt的 ，或者集成在在Ruby中Tk的的例子。
*  使用end关键字结束代码块，而不使用括号。
*  你应使用require 替换import关键字 。
*  所有的成员变量都是私有的。你通过方法访问类的一切变量。
*  在方法调用的括号通常是可选的，往往省略。
*  一切都是对象，包括像2和3.14159这样的数字。
*  没有静态类型检查。
*  变量名都只是标签。它们不具有与它们相关联的类型。
*  有没有类型声明。你只是根据需要分配新的变量名，例如"spring up"（即a = [1,2,3]而不是int[] a = {1,2,3};
*  没有强制转换。只有方法可调用。你运行的代码，如果发生一个异常。单元测试应该告诉你。
*  通过foo = Foo.new("hi")取代Foo foo = new Foo("hi")
*  构造函数始终命名为“initialize”，而不是类的名称。
*  使用“mixins”替换接口。
*  YAML往往更优先于XML。
*  这是nil ，而不是null 。
*  ==和equals()在Ruby的 ​​处理方式不同。}当你想测试等价的Ruby中使用=={/0（ equals()是Java的）。当你想知道两个对象是相同时使用用equal?()（ ==在Java中）。
