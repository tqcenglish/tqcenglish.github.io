title: CNode 部署
date: 2018-08-25
tags:  Node.js
---
CNode 是国内基于 node, mongodb, redis, express, ers 技术栈构建的一个论坛程序。 egg-cnode 将 express 替换为 egg.js 框架.

## [egg-cnode](https://github.com/cnodejs/egg-cnode)
cnode 论坛的 egg 实现版本， 后端服务由原来的 Express 切换为 Node. 在部署过程中主要安装如下软件。

- redis
- mongoldb
- nvm
- node

## 调试模式不发送邮件(多种原因导致)
- 发送邮件被屏蔽
- 调试模式下发送邮件直接返回
- 163 需要授权码登录
- 激活回调地址 config.host 配置

可以直接修改数据库为激活模式登录




