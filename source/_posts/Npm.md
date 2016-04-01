title: Npm使用以及相关软件
date: 2016-02-20 01:00:33
tags: npm
---
# Npm 使用
# 软件
* [supervisor](https://github.com/Supervisor/supervisor) 监控代码修改，自动重启 node.js
* [pm2] 对应用进行发布，监控。
* [node-inspector] 调试
* [hubot](https://github.com/github/hubot)

# 文章
* [发布node.js项目](https://github.com/i5ting/node-deploy-practice)
* [五款 Slack 开源替代品](http://www.oschina.net/question/2012764_2141029)


#[NPM](https://www.npmjs.com/)
了解NPM大致功能。
## 开始

### NPM是什么？
NPM让JS代码容易分享和复用，对于你分享的代码非常容易保持更新。

### 安装Node.js和更新npm
Node.js的安装可以通过[官网](https://nodejs.org/en/)或[Linux 分发](https://github.com/nodesource/distributions)安装。
＊使用nvm＊
npm 要求 node 版本大于0.10.32

### 更新 npm
node的安装同时包含了npm， 如果需要最新版本的npm通过
```bash
sudo npm install npm -g
```

### 手动安装 npm

## 修复npm安装权限
安装全局包过程出现**EACCES**说明你没有向npm安装全局包和命令的文件路径的写权限。通过两种方式可以修复这个问题：
1. 改变npm默认安装目录权限。
2. 改变npm默认安装目录到其它目录。

[更多查看](https://docs.npmjs.com/getting-started/fixing-npm-permissions)

## npm安装局部包
npm 安装包有两种方式:局部，全局。
通过require的方式引入局部包，命令行工具使用全局包。
``` bash
npm install <package_name>
```
以上命令会在当前目录创建一个**node_modules**目录(如果不存在)，然后下载包到这个目录。
通过ls 或　dir 命令查看是否成功下。

若未指定版本将下载最新版本。否则通过版本规则下载。
[查看更多](https://docs.npmjs.com/getting-started/installing-npm-packages-locally)

## 使用 package.json
通过创建package.json手动管理局部包。
package.json 必须包含的内容

- 'name'
- 'version'

###创建package.json
[查看更多](https://docs.npmjs.com/getting-started/using-a-package.json)
