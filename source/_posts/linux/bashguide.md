# 目录

1. [基本使用](#1-basic-operations)
1. [Shell 编程]
1. [技巧]
1. [调试]

# 1. 基本使用

## a. `export`

显示所有的环境变量配置。如果需要获取指定环境变量使用 `echo $VARIABLE_NAME`.

```bash
export
```

例子:

```bash
$ export
AWS_HOME = /Users/adnanadnan/.aws

$ echo $AWS_HOME
/Users/adnanadnan/.aws
```

## b. `whatis`

whatis 用于显示用户命令, 系统调用, 库函数和数据手册相关的描述。

```bash
  whatis name
```

例子:

```bash
$ whatis bash
bash(1)                  - GNU Bourne-Again SHell
bashbug(1)               - report a bug in bash
```

## c. `whereis`

## d. `which`

## e. `clear`

清楚当前窗口显示

## 1.1. 文件操作


[bash-guide](https://github.com/Idnan/bash-guide)
[bash-guide-raw](https://raw.githubusercontent.com/Idnan/bash-guide/master/README.md)