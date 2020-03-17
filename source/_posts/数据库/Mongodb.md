title: Mongodb
date: 2018-09-15
tags: database
---

mongo是一个面向文档的数据库，它集合了nosql和sql数据库两方面的特性。所有实体都是在首次使用时创建。

没有严格的事务特性，但是它保证任何一次数据变更都是原子性的。也没有固定的数据模型,mongo以javascript作为命令行执行引擎，所以利用shell进行复杂的计算和查询时会相当的慢。

mongo本身支持集群和数据分片, mongo是c++实现的，支持windows mac linux等主流操作系统. 性能优越，速度快