title: Mysql
date: 2018-09-15
tags: sql
---

Mysql 是免费的关系数据库。

## 数据库使用的最佳方式

- 尽量使用预处理.
- 多条记录操作使用批处理.
- 不使用外连接
- 使用 not exist 替换 not in
- or 不能太多
- 更新操作放在事务最后
- 少用临时表
- distinct 导致不必要的排序

## 数据库优化方式
- show status
- explain
- show profile
- trace
