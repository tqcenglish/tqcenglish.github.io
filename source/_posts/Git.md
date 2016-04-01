title: git
date: 2015-11-25 23:57:25
tags: git
---


# Git操作

## Github 或 Git 相关命令操作
### 删除远程分支
``` bash
git push origin :gh-pages
```


## bitbucket
你的计算机上已经有了一个 Git 仓库？让我们把它推送到 Bitbucket 吧。
cd /path/to/my/repo
git remote add origin git@bitbucket.org:tangqinchao/dolist.git
git push -u origin --all # pushes up the repo and its refs for the first time
git push -u origin --tags # pushes up any tags
