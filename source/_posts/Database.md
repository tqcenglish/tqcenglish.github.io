title: 数据库
date: 2016-04-16
tags: database
---

# 数据库
软件的数据存储离不开数据库。数据库主要有　

- 关系数据库 mysql,sqlite, postgresql
- 非关系数据库 mongoDB, leveldb, rokcsDB, Realm
- 图形数据库

另外最近发现一个时间序列数据库，基于 go 实现。

## [leveldb](http://leveldb.org/)
谷歌开源的k-v数据库。支持主要平台，但缺少相关语言封装。主要封装为 [levelup](https://github.com/Level/levelup)

## [rocksDB](http://rocksdb.org/)
Facebook 在 leveldb 的基础上开源的数据库。 据说更高效。
[github](https://github.com/facebook/rocksdb)
[rocksdb](https://code.facebook.com/projects/577808328939952/rocksdb/)

## [Realm](https://realm.io/)
主要面向移动端的现代数据库。 可以替换 ios 的 CocaData 和 Android 的 Sqlite;

- Realm for Android快速入门教程 [中文](http://www.tuicool.com/articles/V7ZFvuB) [英文](http://code.tutsplus.com/tutorials/up-and-running-with-realm-for-android--cms-25241)
- [github realm-java](https://github.com/realm/realm-java)
- [github realm-cocoa](https://github.com/realm/realm-cocoa)

# Mysql
记录关系数据库 Mysql 的相关学习。
- [MySQL性能优化的最佳20+条经验](http://coolshell.cn/articles/1846.html)
- [MySQL: InnoDB 还是 MyISAM?](http://coolshell.cn/articles/652.html)
- [mysql set log](http://stackoverflow.com/questions/6479107/how-to-enable-mysql-query-log) 数据配置已改变
- [mysql explain用法](http://www.cnblogs.com/linjiqin/p/4125898.html)
- [MySQL not using indexes with WHERE IN clause?](http://stackoverflow.com/questions/586381/mysql-not-using-indexes-with-where-in-clause)
- [mysql表切换引擎的几种方法](http://www.cnblogs.com/loveLearning/archive/2013/04/17/3025502.html)


> 在项目的初期对数据库的选择十分重要，要进行压力测试。 另外一般的数据库 orm 会导致效率下降。 tqcenglish
