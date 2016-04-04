title: Java
date: 2015-12-01 21:34:44
tags: java
---

# 基本语法
## 数组 List 相互转换

* List list = Arrays.asList(ArrayName);
* 将list转换为数组
  (String [])arrayList.toArray(new String[arrayList.size()]);

## UI
基于Java的图形库最主要的有三种，它们分别是Swing、AWT和SWT。其中前两个是Sun随JDK一起发布的，而SWT则是由IBM领导的开源项目（现在已经脱离IBM了）Eclipse的一个子项目。  
SWT的执行效率非常高。这是由于SWT的底层是由C编写的。由于SWT通过C直接调用系统层的GUI API。因此，使用SWT编写GUI程序，在外观上就和使用C++、Delphi（在Windows下）编写的程序完全一样。它的这一点和AWT类似。  
AWT在底层也是使用C直接调用系统层的GUI API。但它们是有区别的，最大的区别可能就是一个是Sun提供的，一个是Eclipse自带的。这就意味着如果使用AWT，只要机器上安装了JDK或JRE，发布软件时无需带其它的库。而如何使用SWT，在发布时必须要自带上SWT的*.dll（Windows版）或*.so(Linux/Unix版)文件以及相关的*.jar包。还有就是它们所提供的图形接口有一些差异。SWT可能更丰富一些，我们可以看看Eclipse的界面就知道了。  但随着Sun对AWT库的不断更新，AWT的图形表现能力也在不断地提高。虽然SWT很强大，但它比较底层。也就是说它的一些功能在使用上还比较低级，不太符合面向对象的特征。因此，在SWT的基础上又开发了JFace。JFace在SWT上进行了一定的扩展。因此，也可说JFace是基于SWT的，就象在VC中使用MFC来包装Win32 API一样。
需要的相关包：

    org.eclipse.swt_3.x.x.jar
        org.eclipse.jface_3.x.x.jar
        org.eclipse.core.runtime_3.x.x.jar
        org.eclipse.ui.workbench_3.x.


#Java基础
下文提到的技术是很老的技术了，需要更新新技术。例如 nio, restful 框架。
##java方向及学习方法

 * 第一阶段：Java基础，包括java语法，面向对象特征，常见API，集合框架；
 * 第二阶段：java界面编程，包括AWT，事件机制，SWING，这个部分也可以跳过，用的时候再看都能来及；
 * 第三阶段：java API：输入输出，多线程，网络编程，反射注解等，java的精华部分；
 * 第四阶段：数据库SQL基础，包括增删改查操作以及多表查询；
 * 第五阶段：JDBC编程：包括JDBC原理，JDBC连接库，JDBC API，虽然现在Hibernate比JDBC要方便许多，但是JDBC技术仍然在使用，JDBC思想尤为重要；
 * 第六阶段：JDBC深入理解高级特性：包括数据库连接池，存储过程，触发器，CRM思想；
 * 第七阶段：HTML语言学习，包括HTML标签，表单标签以及CSS，这是Web应用开发的基础；
 * 第八阶段：JavaScript脚本语言，包括javaScript语法和对象，就这两个方面的内容；
 * 第九阶段：DOM编程，包括DOM原理，常用的DOM元素以及比较重要的DOM编程思想；
 * 第十阶段：Servlet开发，从此开始踏入java开发的重要一步，包括XML，Tomcat服务器的安装使用操作，HTTP协议简单理解，Servlet API等，这个是java web开发的基础。
 * 第十一阶段：JSP开发：JSP语法和标签，自定义标签，EL,JSTL库了解以及MVC三层架构的设计模式理念；
 * 第十二阶段：AJAX开发：AJAX原理，请求响应处理，AJAX开发库；
 * 第十三阶段：轻量级框架，三大框架之一Struts框架的学习，自此踏入java web开发的精华部分，包括Struts体系架构，各种组件，标签库和扩展性的学习；
 * 第十四阶段：Hibernate框架学习，三大框架之一，包括检索映射技术，多表查询技术，缓存技术以及性能方面的优化；
 * 第十五阶段：Spring框架的学习，三大框架之一，包括了IOC,AOP,DataSource，事务，SSH集成以及JPA集成；
 * 最后呢，还有些java的技术，包括EJB3.0等，可以选择学习，与三大轻量级框架相比，EJB就是当之无愧的重量级了。
