title: 交叉编译
date: 2017-1-10
tags: golang
---
 
golang 对 c 有很好的支持。 通过 cgo 可以方便调用 c 语言实现的功能模块。

## 交叉编译 arm 版本 
若代码中包含 cgo 需要使用交叉编译器, 使用 linux x86 平台编译目标 arm 版本。 对 arm 平台需要判断对应的 arm架构

soft   : 不用fpu进行浮点计算，即使有fpu浮点运算单元也不用,而是使用软件模式。
softfp : armel架构(对应的编译器为gcc-arm-linux-gnueabi)采用的默认值，用fpu计算，但是传参数用普通寄存器传，这样中断的时候，只需要保存普通寄存器，中断负荷小，但是参数需要转换成浮点的再计算。
hard   : armhf架构(对应的编译器gcc-arm-linux-gnueabihf)采用的默认值，用fpu计算，传参数也用fpu中的浮点寄存器传，省去了转换, 性能最好，但是中断负荷高。

**OSX 安装教程编译器很麻烦**