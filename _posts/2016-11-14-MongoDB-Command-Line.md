---
layout:    post
title:     "MongoDB Command Line"
subtitle:  "MongoDB Command Line"
date:       2016-11-14 17:35:35
author:     "Gcelaor"
header-img: "img/Responsive.jpg"
catalog: true
tags:
    - MongoDB
---

本文总结了一些常用的[MongoDB](https://mongodb.com/)命令。详细文档可以参考：MongoDB文档：[https://docs.mongodb.com/](https://docs.mongodb.com/)

## 数据库操作

```
# 查看数据库
show dbs
# 切换数据库
use mydatabase
# 查看当前数据库
db
# 删除当前数据库
db.dropDatabase()
```

## 集合操作

```
# 查看集合
show collections
# 删除集合
db.users.drop()

```

## 文档操作

### 插入文档

```
db.users.insert({
    name: 'gcelaor',
    url: 'http://gcelaor.github.io'
})

```

### 查询文档

```
# 查询所有
db.users.find()
# 条件查询
db.users.find({
    name: 'gcelaor'
})
# 有缩进的输出
db.users.find().pretty()

```

### 更新文档

```
db.users.update({
    name: 'gcelaor'
}, {
    url: 'http://gcelaor.github.io'    
})

```

### 删除文档

```
# 删除所有
db.users.remove({})
# 条件删除
db.users.remove({
    url: 'http://gcelaor.github.io'
})
```