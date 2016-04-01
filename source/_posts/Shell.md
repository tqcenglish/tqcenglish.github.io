title: Shell
date: 2016-03-4 22:34:44
tags: shell
---

# Shell
shell 命令简单解释。

## getopts
处理命令行参数

    getopts options variable
getopts 的设计目标是在循环中运行,每次执行循环，getopts 就检查下一个命令行参数,并判断它是否合法。

即检查参数是否以 - 开头，后面跟一个包含在 options 中的字母.如果是,就把匹配的选项字母存在指定的变量 variable 中,并返回退出状态0;如果 - 后面的字母没有包含在 options 中,就在 variable 中存入一个 ?,并返回退出状态0;如果命令行中已经没有参数,或者下一个参数不以 - 开头，就返回不为0的退出状态。

  1. getopts 允许把选项堆叠在一起（如 -ms）
  2. 如要带参数,须在对应选项后加:(如h后需加参数 h:ms),此时选项和参数之间至少有一个空白字符分隔,这样的选项不能堆叠。
  3. 如果在需要参数的选项之后没有找到参数,它就在给定的变量中存入?,并向标准错误中写入错误消息.否则将实际参数写入特殊变量: OPTARG
  4. 另外一个特殊变量: OPTIND,反映下一个要处理的参数索引,初值是1,每次执行 getopts 时都会更新.

  [例子](http://www.cnblogs.com/xiangzi888/archive/2012/04/03/2430736.html)

## bc
计算器

  * ibase用于设置输入数据的进制
  * obase用于输出的数据进制

下面将4按照2进制输出100

    echo "obase=2;4" | bc

## seq
seq -- print sequences of numbers
