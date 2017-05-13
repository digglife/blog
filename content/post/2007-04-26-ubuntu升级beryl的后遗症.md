---
title: Ubuntu:升级beryl的后遗症.
author: 摩摩诘
type: post
date: 2007-04-26T13:59:18+00:00
url: /articles/ubuntu升级beryl的后遗症.html
comment_count:
  - 3
related_posts:
  - 'a:2:{s:4:"time";i:1224857862;s:13:"related_posts";s:1588:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/how-to-install-kde40-in-ubuntu.html" title="如何在Ubuntu 7.10下安装KDE 4.0">如何在Ubuntu 7.10下安装KDE 4.0</a></li><li><a href="http://www.digglife.cn/articles/install-compiz-fusion-and-trouble-shooting-part2-2.html" title="Ubuntu Compiz Fusion安装和常见问题解决 Part.2">Ubuntu Compiz Fusion安装和常见问题解决 Part.2</a></li><li><a href="http://www.digglife.cn/articles/install-compiz-fusion-and-trouble-shooting-part1-2.html" title="Ubuntu Compiz Fusion安装和常见问题解决 Part.1">Ubuntu Compiz Fusion安装和常见问题解决 Part.1</a></li><li><a href="http://www.digglife.cn/articles/run-every-windows-app-on-ubuntu.html" title="利用VMware在Ubuntu下使用已有的Windows软件.">利用VMware在Ubuntu下使用已有的Windows软件.</a></li><li><a href="http://www.digglife.cn/articles/how-to-install-software-in-ubuntu.html" title="Ubuntu技巧:Ubuntu软件安装方法完全指南">Ubuntu技巧:Ubuntu软件安装方法完全指南</a></li><li><a href="http://www.digglife.cn/articles/ubuntu%e6%9c%80%e7%ae%80%e5%8d%95%e7%9a%84ubuntu%e5%ae%89%e8%a3%85%e5%b7%a5%e5%85%b7wubiwindows-xp.html" title="Ubuntu:最简单的Ubuntu安装工具:Wubi(Windows XP)">Ubuntu:最简单的Ubuntu安装工具:Wubi(Windows XP)</a></li><li><a href="http://www.digglife.cn/articles/%e5%9c%a8linux%e4%b8%8b%e4%bd%bf%e7%94%a8beryl%e5%ae%9e%e7%8e%b0vista%e6%95%88%e6%9e%9c.html" title="ubuntu 6.10 edgy beryl安装日志">ubuntu 6.10 edgy beryl安装日志</a></li></ul>";}'
views:
  - 503
bot_views:
  - 1364
duoshuo_thread_id:
  - 1154125469839261738
categories:
  - Ubuntu技巧
tags:
  - ubuntu
  - 安装
  - 故障

---
昨天Ubuntu的自动更新提示我更新120MB左右的文件,仔细看了一下,除了内核和office之外,居然还有beryl.另外,Ubuntu feisty fawn也进入自动更新的推荐安装中.当然我不会傻里傻气在线更新升级Ubuntu,提示信息中的剩余时间会让人吐血的,目前的配置已经用起来很舒服了,重新安装新版本的代价比较大,所以还是更新了常规文件.

结果马上出现了问题.

  * 启动出现无法装载human.xml的信息.
  * 启动beryl X window重启
  * 启动wine X window重启

罪魁祸首 beryl0.20RC3

[![beryl.png][1]][2]

我以为是主题文件丢失导致的,于是从Ubuntu安装盘上复制了Human,HumanCircle,HumanList三个文件替换了原文件.结果证明无效.只好采取鸵鸟政策,把登录界面改为&#8221;欢乐GNOME&#8221;.

后来想到更新文件中的office不会影响这个,只有可能是beryl更新造成.想到安装beryl的时候手动安装显卡驱动,记得说明里面提到更新内核需要重新安装驱动,于是想到Beryl更新之后是不是也要重新安装.

所以尝试**重新安装NVIDIA显卡驱动**,果然问题解决.

 [1]: http://digglife.qiniudn.com/wp-content/uploads/3/379/2007/04/beryl.thumbnail.png
 [2]: https://www.digglife.net/wp-content/uploads/3/379/2007/04/beryl.png "beryl.png"