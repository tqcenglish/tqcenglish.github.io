title: Hexo
date: 2015-11-01 01:36:33
tags: hexo;blog
---

# 在 Github 中搭建 Hexo 博客

## 安装
参考[官网](https://hexo.io/), [中文文档](https://hexo.io/zh-cn/docs/),[插件使用](https://hexo.io/zh-cn/docs/tag-plugins.html)

## 部署步骤
``` bash
hexo clean
hexo generate
hexo deploy

```
### 本地调试
``` bash
hexo deploy -g  生成加部署
hexo server -g  生成加预览 (hexo s -g)
```
## 命令简写
``` bash
hexo n == hexo new
hexo g == hexo generate
hexo s == hexo server
hexo d == hexo deploy
```

对 hexo server -p 8080 可以修改运行端口。
# 引用
* http://www.cnblogs.com/zhcncn/p/4097881.html
* [next主题设置](http://theme-next.iissnan.com/)
