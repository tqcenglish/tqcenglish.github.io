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
