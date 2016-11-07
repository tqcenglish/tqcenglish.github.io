title: Tmux
date: 2016-11-7 
tags: soft
---

> tmux is a terminal multiplexer
> Tmux 是一个工具，用于在一个终端窗口中运行多个终端会话。

## [Tmux](http://tmux.github.io/)

### 会话
一个 Tmux 会话中可以包含多个窗口.

```
tmux new -s <name-of-my-session> // 创建第一个会话
Ctrl-b : && new -s <name-of-my-session> // 创建新会话
Ctrl-b s // 切换会话,列出所有会话
tmux attach -t test //进入名为test的session
C-b d // detach当前session(可以认为后台运行)
```

### 其他快捷键
Window操作

  C-b c 创建一个新窗口
  C-b & 关闭当前窗口
  C-b w 列出所有的窗口选择
  C-b p 切换到上一个窗口
  C-b n 切换到下一个窗口
  C-b 窗口号 使用窗口号切换窗口(例如窗口号为1的, 则C-b 1)
  C-b , 重命名当前窗口，便于识别各个窗口

Pane操作

  C-b % 横向分Terminal
  C-b " 纵向分Terminal
  C-b 方向键 则会在自由选择各面板
  C-b x 关闭当前pane
  C-b q 显示面板编号

## 链接
* http://blog.jobbole.com/87584/
* http://www.linuxidc.com/Linux/2015-07/119843.html
* https://github.com/gpakosz/.tmux //   