---
title: 如何在Ubuntu 7.10下安装KDE 4.0
author: 摩摩诘
type: post
date: 2008-01-13T16:00:56+00:00
url: /articles/how-to-install-kde40-in-ubuntu.html
0:
  - dc44fc34016ae6de6ce2bb1c31ee7684d7c287f265bba040ed0d5698dee930d5d6b9a01139b4444fc78a8623ad64210e
1:
  - 5242c54db1242eb9f005c51d589806af059aa25d928d66924e7539b903227700e46bb995cd82c6764df39a76191ab0c3
2:
  - 2394dfaa80353d8c0b93ba5444f0906f809b46cb13dc700c0d50eae3bbe0e407a56b9a64a112f8a8e724c57a158b2700
3:
  - 63db217f956f59cc7a504d36818a35a20d66cef579e3f29ed89e333b2a552757b4a16fc7e6f0f72338f153b93faddb10
keywords:
  - kde 4.0, kubuntu, Linux, ubuntu, 安装, 技巧
description:
  - 现在网上已经有预装有KDE 4.0.0的Linux发行版下载,不过对于Ubuntu用户来说,更加实际的问题是如何直接在现有的Ubuntu下体验全新的KDE 4.0.下面提供安装方法,其实和之前安装KDE的方法没有什么区别,只需要添加一个软件源即可.
comment_count:
  - 5
related_posts:
  - 'a:2:{s:4:"time";i:1224889571;s:13:"related_posts";s:1518:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/install-compiz-fusion-and-trouble-shooting-part2-2.html" title="Ubuntu Compiz Fusion安装和常见问题解决 Part.2">Ubuntu Compiz Fusion安装和常见问题解决 Part.2</a></li><li><a href="http://www.digglife.cn/articles/install-compiz-fusion-and-trouble-shooting-part1-2.html" title="Ubuntu Compiz Fusion安装和常见问题解决 Part.1">Ubuntu Compiz Fusion安装和常见问题解决 Part.1</a></li><li><a href="http://www.digglife.cn/articles/ubuntu-easter-eggs.html" title="Ubuntu复活节彩蛋">Ubuntu复活节彩蛋</a></li><li><a href="http://www.digglife.cn/articles/make-openoffice-run-faster-in-ubuntu.html" title="加快Open Office在Ubuntu中的运行速度">加快Open Office在Ubuntu中的运行速度</a></li><li><a href="http://www.digglife.cn/articles/how-to-install-software-in-ubuntu.html" title="Ubuntu技巧:Ubuntu软件安装方法完全指南">Ubuntu技巧:Ubuntu软件安装方法完全指南</a></li><li><a href="http://www.digglife.cn/articles/ubuntu%e6%9c%80%e7%ae%80%e5%8d%95%e7%9a%84ubuntu%e5%ae%89%e8%a3%85%e5%b7%a5%e5%85%b7wubiwindows-xp.html" title="Ubuntu:最简单的Ubuntu安装工具:Wubi(Windows XP)">Ubuntu:最简单的Ubuntu安装工具:Wubi(Windows XP)</a></li><li><a href="http://www.digglife.cn/articles/ubuntu%e8%ae%a9%e6%a1%8c%e9%9d%a2%e6%98%be%e7%a4%ba%e5%9b%9e%e6%94%b6%e7%ab%99.html" title="Ubuntu:让桌面显示回收站">Ubuntu:让桌面显示回收站</a></li></ul>";}'
views:
  - 1857
bot_views:
  - 2383
duoshuo_thread_id:
  - 1154125469839262016
categories:
  - Ubuntu技巧
tags:
  - kde 4.0
  - Linux
  - ubuntu
  - 安装

---
[<img src="https://www.digglife.net/wp-content/uploads/3/379/2008/01/windowslivewriterubuntu7.10kde4.0-1437bkdelogo-thumb.png" alt="kdelogo" align="right" border="0" height="100" width="100" />][1] 备受瞩目的KDE 4的第一个稳定版KDE 4.0.0前几天终于<a href="http://linuxtoy.org/archives/kde-400-released.html" title="KDE 4.0.0 发布" target="_blank">正式发布</a>.&#8221;KDE 4 不仅带来了一系列新的技术，包括 Solid、Phonon、Decibel 等，而且具有全新的桌面外观，如桌面外壳 Plasma、外观界面 Oxygen。同时，KDE 4 也引入了一些新的应用程序，像文件管理器 Dolphin、文档查看器 Okular、桌面地球仪 Marble、图片查看器 Gwenview，等等。另外，一些 KDE 程序在 KDE 4 中得到了显著地增强，如窗口管理器 KWin 获得了复合特性、对 Konsole 控制台进行了整修等。而更多的 KDE 程序或已移植到 KDE 4 平台 (如 Amarok 2、Ktorrent)，或正在向 KDE 4 平台移植。&#8221;

<!--more-->

[<img src="https://www.digglife.net/wp-content/uploads/3/379/2008/01/windowslivewriterubuntu7.10kde4.0-1437bkde-4-0-thumb.png" alt="kde-4_0" border="0" height="220" width="400" />][2]

现在网上已经有预装有KDE 4.0.0的Linux发行版下载,不过对于<a href="https://www.digglife.net/articles/category/about_ubuntu" title="Ubuntu技巧" target="_blank">Ubuntu</a>用户来说,更加实际的问题是如何直接在现有的Ubuntu下体验全新的KDE 4.0.下面提供安装方法,其实和之前安装KDE的方法没有什么区别,只需要添加一个软件源即可.

  * 编辑Source.list文件以添加软件源.打开终端,输入:

          <font color="#000000"></font>sudo gedit /etc/apt/sources.list

          <font color="#000000">系统会提示输入管理员密码,输入后继续.</font>

  * 在弹出的源列表中添加: <font color="#ff5809">deb http://ppa.launchpad.net/kubuntu-members-kde4/ubuntu gutsy main</font><font color="#000000">.</font> <font color="#000000">保存退出.</font>
  * 升级软件源.回到终端输入 <font color="#ff5809">sudo apt-get update</font>
  * 安装KDE 4.0.在终端输入 <font color="#ff5809">sudo apt-get install kde4-core</font>

需要下载大约125MB的安装文件,尝试了一下电信的速度,还算不错.

安装完成并重启后,你就会在登陆界面看到KDE 4的选项了.

同时,如果你想直接安装**预装有KDE 4.0的Kubuntu 7.10**,可以直接下载最新的Live CD:

<a href="http://cdimage.ubuntu.com/kubuntu/releases/gutsy/kde4/kubuntu-kde4.0-i386.iso" title="预装KDE4.0的Kubuntu 7.10下载" target="_blank">预装KDE4.0的Kubuntu 7.10下载</a>

 [1]: https://www.digglife.net/wp-content/uploads/3/379/2008/01/windowslivewriterubuntu7.10kde4.0-1437bkdelogo-2.png
 [2]: https://www.digglife.net/wp-content/uploads/3/379/2008/01/windowslivewriterubuntu7.10kde4.0-1437bkde-4-0-2.png
