# 铃羊挂角

tqcenglish 是 tangqinchao 的 english 名。

## 安装

安装 [hexo](https://hexo.io/zh-tw/)

``` shell
npm install hexo-cli -g
```

子模块 [hexo-theme-next](https://github.com/iissnan/hexo-theme-next) 安装。

``` shell
git submodule update --init --recursive
```

## 使用与发布

预览

``` shell
hexo server
```

发布

``` shell
hexo clean
hexo generate
hexo deploy
```

## 错误处理

1. 更新 hexo 全局版本
1. 不用 yarn
