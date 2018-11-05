---
title: 加快Open Office在Ubuntu中的运行速度
author: 摩摩诘
type: post
date: 2007-06-28T01:37:36+00:00
url: /articles/make-openoffice-run-faster-in-ubuntu.html
0:
  - 898b16ee762b862be988cb5bf93b5bccf97066acc575ed2ccbe0fa1f63b87c388c5713f1f3c40664afe7572653b048ee
  - 898b16ee762b862be988cb5bf93b5bccf97066acc575ed2ccbe0fa1f63b87c388c5713f1f3c40664afe7572653b048ee
1:
  - 42426e66217a6d906c9f15c2043bc89e6861f3b1c88d720ad7544961cae3898c6c63be69f1d70860144c2a2eabc4a545
  - 42426e66217a6d906c9f15c2043bc89e6861f3b1c88d720ad7544961cae3898c6c63be69f1d70860144c2a2eabc4a545
comment_count:
  - 2
related_posts:
  - 'a:2:{s:4:"time";i:1224884007;s:13:"related_posts";s:1356:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/ubuntu%e8%ae%a9%e6%a1%8c%e9%9d%a2%e6%98%be%e7%a4%ba%e5%9b%9e%e6%94%b6%e7%ab%99.html" title="Ubuntu:让桌面显示回收站">Ubuntu:让桌面显示回收站</a></li><li><a href="http://www.digglife.cn/articles/how-to-install-kde40-in-ubuntu.html" title="如何在Ubuntu 7.10下安装KDE 4.0">如何在Ubuntu 7.10下安装KDE 4.0</a></li><li><a href="http://www.digglife.cn/articles/ubuntu-easter-eggs.html" title="Ubuntu复活节彩蛋">Ubuntu复活节彩蛋</a></li><li><a href="http://www.digglife.cn/articles/clean-up-desktop-improve-productivity-2.html" title="彻底清空桌面,让启动程序更加高效Part.2">彻底清空桌面,让启动程序更加高效Part.2</a></li><li><a href="http://www.digglife.cn/articles/clean-up-desktop-improve-productivity-1.html" title="彻底清空桌面,让启动程序更加高效Part.1">彻底清空桌面,让启动程序更加高效Part.1</a></li><li><a href="http://www.digglife.cn/articles/top10-greasemonky-scripts-for-gmail20.html" title="10个增强Gmail新版体验的Greasemonkey代码">10个增强Gmail新版体验的Greasemonkey代码</a></li><li><a href="http://www.digglife.cn/articles/five-windows-explorer-tweaks.html" title="5大Windows Explorer优化技巧">5大Windows Explorer优化技巧</a></li></ul>";}'
bot_views:
  - 1956
views:
  - 1541
duoshuo_thread_id:
  - 1154125469839261826
categories:
  - Ubuntu技巧
tags:
  - Linux
  - openoffice
  - ubuntu
  - 优化

---
觉得OpenOffice运行的很慢?通过以下简单的设置能够让你的OpenOffice运行的更快.测试效果显著.

1.打开open office文字处理.(应用程序&#8211;办公&#8211;Open Office.org文字处理)

2.在菜单栏中选择工具&#8211;选项.

3.定位到内存选项.将参数改为如下设置.

<img width="450" src="https://www.digglife.net/wp-content/uploads/3/379/2007/06/memory1.png" alt="memory" height="195" /> 

>   * **撤销命令**下的**步数**:20-30
>   * **图形缓冲区下**的**用于OpenOffice.org**:128MB(原始值为6MB)
>   * **每个对象的内存**:20.0MB
>   * **给插入对象的缓冲区**下的**对象的数目**:20
>   * 勾选**启用系统盘快速启动程序**

4.定位到Java选项.把**使用Java运行时的环境**前的勾去掉

<img width="450" src="https://www.digglife.net/wp-content/uploads/3/379/2007/06/java.png" alt="java" height="195" />

5.点击确定保存.重启体验一下吧.

来自<a target="_blank" href="http://www.zolved.com/">zolved</a>
