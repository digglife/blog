---
author: 摩摩诘
categories:
- 代码卷轴
date: 2018-10-24T09:55:12+08:00
tags:
- sqlalchemy
- python
- oracle
title: SQLAchemy 连接 Oracle 数据库的坑
url: /articles/sqlalchemy-oracle.html

---

公司一个项目要用 Flask 来写 Web 后台，数据库用的是 Oracle，我心想 Oracle 我从来没玩过，还是像 Django 那样用 ORM 来吧。Flask 虽然是个微框架，只干该干的事，但是有些插件其实是有类官方地位的，比如 Defacto ORM 就是 SQLAlchemy，结果我踩了不少「匪夷所思」的坑。
<!--more-->

### 数据库链接 URL 的问题

SQLAlchemy 有个子模块可以根据数据库的一些属性来生成连接数据库的 URL。比如我们可以这样生成一个 URL：

```python
from sqlalchemy.engine.url import URL

config = {
  "drivername": "oracle",
  "host": "127.0.0.1",
  "port": "1521"
  "database": "default",
  "username": "admin",
  "password": "admin",
}

db_uri = URL(**config)
# oracle://admin:admin@127.0.0.1:1521/default
```

问题是，用这么一个 URL，你是连不上 Oracle 数据库的，为什么？因为 Oracle 数据库有特殊性。正确的写法是:

```bash
oracle://admin:admin@127.0.0.1:1521/?service_name=default
```

事实上，Oracle 自己的官方 Python Binding，也就是 [cxOracle](https://oracle.github.io/python-cx_Oracle/)，是不会这么生成 URL 的。


### SQLAlchemy-Utils 判断数据库是否存在的问题

[SQLAlchemy-Utils](https://github.com/kvesteri/sqlalchemy-utils) 是 SQLAlchemy 的一个知名周边，提供了一些非常方便的函数和数据类型，比如和初始化相关的一些函数。

其中有一个 `database-exists` 的函数，会判断指定的数据库是否存在，但是这个函数在 Oracle 下会报错。
原因是用来判断数据库是否存在的语句是 `SELECT 1;`，然而 Oracle 是不支持这个语句的，正确的写法应该是
`SELECT 1 FROM DUAL`，其中 `DUAL` 是 Oracle 数据库在安装过程中生成的默认表单。

### 抽象和细节的平衡

我们用 ORM 有一部分的理由是为了隐藏 SQL 细节，但是如果连第一步的正确执行都无法保证，还需要去深入了解
代码细节，那还不如从一开始就写 Raw SQL 吧。

另外，Flask 号称 Micro，但实践中我如果要快速搭建一个靠谱的 App，还是需要导入若干个有官方地位的扩展，
而这些扩展的文档，都不会和 Flask 本身有紧密的照应，可以说是支离破碎，对于我这种曾经用过 Django 的人来说，
很多东西可以猜到，但是对于初学者，怕并不是那么友好。



