---
title: Ubuntu技巧:Ubuntu软件安装方法完全指南
author: 摩摩诘
type: post
date: 2007-06-05T13:43:04+00:00
url: /articles/how-to-install-software-in-ubuntu.html
comment_count:
  - 4
related_posts:
  - 'a:2:{s:4:"time";i:1224872725;s:13:"related_posts";s:1668:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/how-to-install-kde40-in-ubuntu.html" title="如何在Ubuntu 7.10下安装KDE 4.0">如何在Ubuntu 7.10下安装KDE 4.0</a></li><li><a href="http://www.digglife.cn/articles/install-compiz-fusion-and-trouble-shooting-part2-2.html" title="Ubuntu Compiz Fusion安装和常见问题解决 Part.2">Ubuntu Compiz Fusion安装和常见问题解决 Part.2</a></li><li><a href="http://www.digglife.cn/articles/install-compiz-fusion-and-trouble-shooting-part1-2.html" title="Ubuntu Compiz Fusion安装和常见问题解决 Part.1">Ubuntu Compiz Fusion安装和常见问题解决 Part.1</a></li><li><a href="http://www.digglife.cn/articles/ubuntu%e5%a6%82%e4%bd%95%e5%9c%a8ubuntu%e4%b8%ad%e5%ae%89%e8%a3%85ie%e6%94%af%e6%8c%81feisty-fawn-edgy-eft-%e5%92%8cdapper-drake.html" title="Ubuntu:如何在Ubuntu中安装IE(支持Feisty Fawn, Edgy Eft 和Dapper Drake)">Ubuntu:如何在Ubuntu中安装IE(支持Feisty Fawn, Edgy Eft 和Dapper Drake)</a></li><li><a href="http://www.digglife.cn/articles/ubuntu-windows-xp-vista-firefox-profile.html" title="Ubuntu,Windows Vista和XP共享Firefox配置文件">Ubuntu,Windows Vista和XP共享Firefox配置文件</a></li><li><a href="http://www.digglife.cn/articles/clean-up-desktop-improve-productivity-2.html" title="彻底清空桌面,让启动程序更加高效Part.2">彻底清空桌面,让启动程序更加高效Part.2</a></li><li><a href="http://www.digglife.cn/articles/clean-up-desktop-improve-productivity-1.html" title="彻底清空桌面,让启动程序更加高效Part.1">彻底清空桌面,让启动程序更加高效Part.1</a></li></ul>";}'
views:
  - 110154
bot_views:
  - 5205
dsq_thread_id:
  - 6892756
duoshuo_thread_id:
  - 1154125469839261797
categories:
  - Ubuntu技巧
tags:
  - ubuntu
  - 安装
  - 软件

---
刚开始使用Ubuntu的用户时常有这样的问题,我要安装新软件怎么办?.exe文件在哪里,怎么软件有这么多格式?RPM包,.tar.gz是什么?怎么就是安装不了啊?等等等等.<a href="https://www.digglife.net/wp-content/uploads/3/379/2007/06/logo.png" atomicselection="true"><img height="55" alt="logo" src="https://www.digglife.net/wp-content/uploads/3/379/2007/06/logo-thumb.png" width="202" align="right" /></a> 的确,在Windows下安装文件只需要双击即可,所以很多人在Ubuntu下觉得很不习惯.事实上,使用Ubuntu平台下的新利得软件包管理器安装大部分软件比在Windows平台下更加简单,操作更加容易.当然,也有很多软件Ubuntu的储藏库里面没有,而这些软件有着各式各样的格式,因而安装方法也都不一样.下面我就Ubuntu下安装软件的方法做一个详细的总结.

### **一.使用新立得软件包管理器安装程序.**

新立得拥有一个友好的图形界面,你可以使用它安装大部分Ubuntu软件库里已有的程序.定位到系统-系统管理-新立得软件包管理器 启动,基于安全考虑,系统会提示你输入管理员密码.在这里,你可以搜索你需要安装的程序,标记后应用即可.

**3步安装:搜索,标记,应用**

  1. 搜索你需要安装的程序.在新立得里面有成千上万种主题,应用程序,软件包,文档.所有的这些文件包都被存放在Ubuntu的服务器上供下载和升级.新立得相当于一个升级版的windows升级工具,因为它除了可以升级系统文件之外,还可以通过它安装的非关键性程序.你可以在侧边栏的分类中查找软件.点击工具栏上的搜索图标进行搜索. <a href="https://www.digglife.net/wp-content/uploads/3/379/2007/06/.png" atomicselection="true"><img height="354" alt="新立得" src="https://www.digglife.net/wp-content/uploads/3/379/2007/06/thumb.png" width="450" /></a>
  2. 找到需要安装的文件包后,右键点击标记.系统很有可能会提示你一些依赖程序将会同时被安装,幸运的是这些系统会自动为你解决.记住:你可以使用同样的步骤卸载程序(右键点击,选择卸载).你也可以一次标记多个安装包以节省时间.
  3. 标记完毕所有需要安装的文件之后,点击应用图标.新立得会自动下载安装.

<!--more-->



**常见问题:**

<font color="#ff0080">1.如果找不到我需要的文件怎么办?</font>
其实这是很正常的.大概说来有以下3个原因:

  * 新立得软件包管理器里面的所有文件包都来自Ubuntu的主源,但是除了默认的源之外还有很多非官方软件源.在你放弃安装之前尝试一下激活额外的源.
  * 如果你没有联网,这样的结果是肯定的.当然,你也许能够在安装CD上找到它,不过基本上这样的可能性比较小.
  * 如果你在非官方源都无法找到该文件包,你还可以手动安装.但是记住,在Linux下有比你想象中多得多的安装包格式.这也是本文重点介绍的部分.

<font color="#ff0080">2.我已经安装了,但是我在哪里才能找到它呢?</font>
通常情况下,应用程序菜单会自动升级以包含你安装的文件,但是有时也不会.这里有几种方法找到你新安装的程序.
1).安装Debian Menu.

Debian Menu给你安装的程序提供了一个更加全面的列表,它同样显示在应用程序菜单里.你需要安装一个叫做menu-xdg的软件包(新立得里面有),可能需要重启X window(Ctrl+Alt+空格)才能让它显示.

<a href="https://www.digglife.net/wp-content/uploads/3/379/2007/06/debian-menu.png" atomicselection="true"><img height="149" alt="Debian_menu" src="https://www.digglife.net/wp-content/uploads/3/379/2007/06/debian-menu-thumb.png" width="316" /></a>

2).在终端输入程序名.

<a href="https://www.digglife.net/wp-content/uploads/3/379/2007/06/2007-06-05-062239-561x463-scrot.png" atomicselection="true"><img style="border-right: 0px; border-top: 0px; border-left: 0px; border-bottom: 0px" height="371" alt="2007-06-05-062239_561x463_scrot" src="https://www.digglife.net/wp-content/uploads/3/379/2007/06/2007-06-05-062239-561x463-scrot-thumb.png" width="450" border="0" /></a>

比如说我通过新立得安装了**Muine**,然后可以通过在终端直接输入**Muine**,回车就可以启动它了.注意,这样操作得话,程序会随着你关闭终端而自动关闭. 为避免这种情况发生,同时按下**Alt+F2**运行**启动程序管理**,输入muine启动.你还可以尝试键入程序名称的首字母后按两下Tab键.输入框会显示命令名称或者可供选择的命令列表.要知道程序的命令行名称可以按照一下步骤:
在新立得里面右键点击安装包,选择属性后进入&#8221;已安装文件&#8221;标签栏.这里显示的是已安装的程序列表,安装到/**usr/bin文件夹**的文件绝大多数情况就是该程序的命令名.

<font color="#ff0080">3.我该如何卸载这些程序呢.</font>
当你要卸载一个程序时,和安装该程序的步骤一样,只是要选择&#8221;标记以便删除&#8221;,而不是&#8221;标记以便安装&#8221;.如果你想把配置文件一并删除,则可以选择&#8221;标记以便彻底删除&#8221;.

### **二.使用终端安装软件.**

可能你会经常看到这样的话:你可以使用以下代码安装某某程序&#8230;然后在下面提供一段可以直接复制到终端的代码.你可能觉得这和新立得完全不同,而事实上,新立得同样在使用这样的代码,只不过给了一个友好的界面而已.

安装方法:
定位到应用**<font color="#000080">程序&#8211;附件&#8211;终端</font>**,激活终端程序.
以下的两行代码是安装程序最常用的命令.

> sudo apt-get install ABC 和 sudo aptitude install ABC

当然,上面的ABC只是虚构的软件.Sudo表示你授权管理员(超级用户)权限给下面的命令.这需要你输入管理员密码.这和你打开新立得的时候需要输入密码是一样的道理,只不过现在是在终端下而已.如果你直接输入sudo aptitude,你会看到一个类似于命令行版本的新立得软件包管理器.

<a href="https://www.digglife.net/wp-content/uploads/3/379/2007/06/aptitude1.png" atomicselection="true"><img height="268" alt="aptitude" src="https://www.digglife.net/wp-content/uploads/3/379/2007/06/aptitude-thumb.png" width="450" /></a>

你还可以像在新立得里面搜索软件一样使用命令行搜索.命令如下:

> apt-cache search ABC 或者 aptitude search ABC

删除软件包命令:

> sudo apt-get remove ABC 和 sudo aptitude remove ABC

同时删除配置文件:

> sudo apt-get remove &#8211;purge ABC 和&nbsp; sudo aptitude purge ABC

虽然命令行可能让很多Linux新用户感到害怕,但是正如你所看到的,它同样非常简单易用,而且和图形界面的新立得有很多共通之处.很多用户更喜欢在终端里安装软件,也有很多喜欢在新立得安装.你可以按自己的喜好选择.如果你决定在Ubuntu下常驻,那么还是多用用命令行吧.

下面是本文的重头戏:

### 三.手动安装软件包

你肯定无法在新立得里面找到自己需要的软件了?你试过激活更多的额外源么?如果你都常试过了都无法找到的话,那么我们就要使用你在Windows下经常使用的招数了.下载安装包然后手动安装.

**1.安装Debian包(.deb)**
其实你在新立得软件包管理器里面下载的所有软件都是Debian软件包.所以如果你在网上找到的程序有几种格式供下载的时候,最简单的就是下载Debian包.

安装方法:

1).让系统自动安装.

你只需要双击下载的Debian包,安装工具就会自动启动.点击&#8221;安装软件包&#8221;执行安装即可.如果有依赖软件需要安装或者软件源里有更新的版本可供安装,它会自动提示你.

<a href="https://www.digglife.net/wp-content/uploads/3/379/2007/06/debian-package-install.png" atomicselection="true"><img height="345" alt="debian_package_install" src="https://www.digglife.net/wp-content/uploads/3/379/2007/06/debian-package-install-thumb.png" width="450" /></a>

2).使用dpkg命令.

我们假设你下载的软件包test.deb在桌面,你的用户名是neo,那么安装命令就是:

> dpkg -i /home/neo/desktop/test.deb

注意:使用此命令需要你自己注意依赖软件,所以这并不是安装软件的最佳方法.

**2.安装rpm软件包(.rpm)**
RPM是另外一个流行的软件打包方式,它在很多流行的Linux发行版如Fedora,SUSE,Mandriva等上应用得非常广泛.它并没有被 Ubuntu的软件包管理器所采用,但是有一个命令能够将其转化为Deb格式,尽管如此,这并不代表所有的RPM包都能在你的系统上正常运行.同样的软件可以直接安装RPM包,这个包叫做alien,你可以在新立得(当然命令行也可以)里面下载安装它:

> sudo apt-get install alien

那么,RPM的安装方法:
如果用户neo需要安装放在桌面的名叫test.rpm的软件包,只需要在终端中输入

> sudo alien -i /home/neo/desktop/test.rpm

**3.安装桌面主题(.tar, .tar.gz, .tgz, .tar.bz, &#8230;)**
在Gnome下安装桌面主题非常简单.定位到 **<font color="#0000a0">系统&#8211;首选项&#8211;主题</font>** 打开**主题管理器**.使用这个应用程序你可以更改图标,控件,窗口边框等.下载主题包后只需要将其拖拽到主题管理器窗口即可安装.

<a href="https://www.digglife.net/wp-content/uploads/3/379/2007/06/ubuntu-desktop-themes.png" atomicselection="true"><img height="486" alt="ubuntu_desktop_themes" src="https://www.digglife.net/wp-content/uploads/3/379/2007/06/ubuntu-desktop-themes-thumb.png" width="450" /></a>

**4.启动画面主题.(.tar, .tar.gz, .tgz, .tar.bz, &#8230;)
** 这个和安装桌面主题一样简单.定位到 **<font color="#000080">系统&#8211;系统管理&#8211;登录窗口</font>** 打开登录窗口首选项.拖拽下载的主题到这个窗口,在弹出对话框中点击确认即可.

<a href="https://www.digglife.net/wp-content/uploads/3/379/2007/06/login-themes.png" atomicselection="true"><img height="509" alt="login_themes" src="https://www.digglife.net/wp-content/uploads/3/379/2007/06/login-themes-thumb.png" width="450" /></a>

> 介绍两个比较火的Gnome主题网站:
>
> <a href="http://www.gnome-look.org/" target="_blank">Gnome-Look</a>
>
> <a href="http://art.gnome.org/" target="_blank">Gnome Art</a>

**5.源码包 (.tar, .tar.gz, .tgz, .tar.bz, &#8230;)**

待续&#8230;.
