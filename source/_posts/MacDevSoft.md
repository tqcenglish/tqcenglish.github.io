title: MacDevSetup
date: 2016-03-05 20:42:25
tags:
    - soft
    - mac
---
# Mac 开发环境配置

## Mac-dev-setup
* [Mac-dev-setup 中文](https://github.com/Aaaaaashu/Mac-dev-setup) 没有更新
* [Mac-dev-setup 英文](https://github.com/sb2nov/mac-setup)

对 Mac-dev-setup  中的软件进行筛选。

- **Dash** API查询,收费
- **Sketch** UI设计，收费
- **Pocket** 阅读缓存
- **CheatSheet** 查询当前程序快捷键
- **Heroku** Web 托管
- **Homebrew**

git 配置账号
{% codeblock lang:shell %}
    $ git config --global user.name "Your Name Here"
    $ git config --global user.email "your_email@youremail.com"
{% endcodeblock %}


# brew 用法

Homebrew的可执行命令是brew，其基本使用方法如下（以wget为例）。
```
brew search wget // 查找软件包
brew install wget //安装软件包
brew list //列出已安装的软件包
brew remove wget //删除软件包
brew info wget //查看软件包信息
brew deps wget //列出软件包的依赖关系
brew update //更新brew
brew outdated //列出过时的软件包（已安装但不是最新版本）
brew upgrade //更新过时的软件包（全部或指定）
brew upgrade wget//更新过时的软件包（全部或指定）
```
