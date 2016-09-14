---
layout: post
title:  "代码评审"
date:   2016-07-26 11:45:04
categories: 软件
---

代码评审是指对代码进行审核，当符合要求后才合并到主分支中。

代码评审需要借助评审工具完成，对评审进行管理。
# [git-appraise](https://github.com/google/git-appraise)
Go 实现的开源软件，与 Git 集成在一起。

在特性分支中执行 `git-appraise request` 将与主分支的差异作为评审的内容。 然后通过 `git-appraise comment ` 对代码进行评价。 若接受代码修改通过 `git-appraise accept`. 最后要在特性分支中进行 `git-appraise submit`.

`git-appraise list ` 可以查看所有提交
`git-appraise show id` 查看详细。

## [git-appraise-web](https://github.com/google/git-appraise-web)

> 一个简单的只读 web 查看界面, 功能十分简单。

**
  代码通过 `go get` 而不是 `git clone ` 方式安装。 需要加载 `Angualrjs.js` 所有需要翻墙。
**

# [gerrit](https://www.gerritcodereview.com/)
基于 JAVA 实现的开源软件。
* [快速安装](https://gerrit-review.googlesource.com/Documentation/install-quick.html)


# [crucible](https://www.atlassian.com/software/crucible)
收费软件。

# 引用
- [wiki](https://en.wikipedia.org/wiki/List_of_tools_for_code_review)
