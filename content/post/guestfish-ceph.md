---
author: 摩摩诘
categories:
- 代码卷轴
date: 2020-06-11T23:11:47+08:00
tags:
- ceph
- openstack
- guestfish
title: 如何用 Guestfish 访问 Ceph 里的镜像或磁盘
url: /articles/guestfish-ceph
draft: true

---

Openstack 使用传统存储的时候，如果我们需要直接查看或者修改镜像文件里的数据，可以使用 Guestfish 直接添加本地文件。
但是如果使用 Ceph 存储集群的话，就没那么直接了。虽然 Guestfish 支持 RBD，也有文档解释如何使用，但是语焉不详。所以在这里记录一下备忘。

<!--more-->

## Guestfish 对 Ceph 的支持