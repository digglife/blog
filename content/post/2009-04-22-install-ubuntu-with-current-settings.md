---
title: 保存现有设置无痛安装Ubuntu 9.04
author: 摩摩诘
type: post
date: 2009-04-22T04:22:09+00:00
url: /articles/install-ubuntu-with-current-settings.html
syntaxhighlighter_encoded:
  - 1
index_image:
  - https://www.digglife.net/wp-content/uploads/IndexImage/ubuntu.gif
bot_views:
  - 2876
views:
  - 5680
duoshuo_thread_id:
  - 1154125469839262142
categories:
  - Ubuntu技巧
tags:
  - Linux
  - ubuntu

---
还有两天[Ubuntu 9.04][1]正式版就要发布了，这个新版本对于普通桌面用户来说有很多显著的改进，包含但不仅限于，新版内核、全新的文件系统Ext4、大大缩短的启动时间、GNOME2.26桌面环境、革命性的桌面通知系统。从之前国内外博客对Beta和RC的测试来看，无论是系统性能还是桌面体验都有了较大的提升，所以我觉得升级是一个不错的选择。

<!--more-->

有两种方法供我们选择，[升级安装][2]和全新安装。因为前者给我留下的都是痛苦的回忆，所以我通常不建议大家采用升级安装的方式。如果现有的这个[Ubuntu][3]已经服役很长时间，被调教的极为顺手，那么完全抛弃重新配置会非常浪费时间，所以为了减少全新安装带给我们时间和数据上的损失，我们需要备份现有数据和设置，包括：已安装的软件包列表，软件源列表，用户文件夹。

具体方法如下，来自[Royal Linuxing][4]:

**安装前的备份：**

  1. 备份已安装软件包列表。
> `sudo dpkg --get-selections > /home/<span style="color: #ff6600;">user</span>/package.selections`

  2. 备份Home下的用户文件夹。
这个文件夹类似于Windows下的Documents And Settings，包含了用户数据和软件个性化设定。如果你已经将Home放在额外的分区，这一步就不必了。复制所有用户文件夹下的所有内容到另外的分区，注意要包含隐藏文件（Ctrl+**H**ide）

  3. 备份软件源列表。将/etc/apt/文件夹下的sources.list拷贝出来保存即可。

**安装后的恢复**

  1. 还原软件源列表。
复制备份的Sources.list文件到新系统的/etc/apt/目录，覆盖原文件，并替换（Ctrl+H）文档中的intrepid为jaunty。然后更新软件源（sudo apt-get update）。

  2. 重新下载安装之前系统中的软件。
如果你安装的软件数量比较多，可能会花费较长时间。

> `sudo dpkg --set-selections /home/package.selections && apt-get dselect-upgrade`

  3. 最后将备份的主文件夹（/home/用户名）粘贴并覆盖现有主文件夹。

用这个方法我们可以基本在不丢失现有系统和软件设置的情况下使用全新的Ubuntu。

 [1]: http://www.ubuntu.com/
 [2]: http://www.ubuntu.com/getubuntu/releasenotes/904overview#Upgrading%20from%20Ubuntu%208.10
 [3]: https://www.digglife.net/articles/category/about_ubuntu "Ubuntu技巧"
 [4]: http://hehe2.net/linuxhowto/howto-fresh-ubuntu-install-without-losing-your-current-settings/