---
title: Perl数据库多线程读写 DBIx::Connector
author: 摩摩诘
type: post
date: 2014-09-23T02:17:01+00:00
draft: true
url: /?p=3882
categories:
  - 代码卷轴
tags:
  - perl
  - 多线程

---
写Perl运维脚本难免要和数据库打交道，一般情况我们直接使用 CPAN 提供的 DBI 配合相应的 DBD 模块就可以满足大部分需求。但是如果遇到多线程读写的情况，单用这两个模块的话，需要手动做一些事情，比较繁琐，而且也不见得做得好。这个时候 DBIx::Connector 这种数据库链接管理模块就能派上用场了。