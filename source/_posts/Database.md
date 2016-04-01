# 数据库
软件的数据存储离不开数据库。数据库主要有　
- 关系数据库 mysql,sqlite
- 非关系数据库 mongoDB, leveldb, rokcsDB, Realm

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
