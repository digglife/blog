---
title: Ubuntu技巧:Ubuntu软件安装方法完全指南(续)
author: 摩摩诘
type: post
date: 2007-08-02T12:05:56+00:00
url: /articles/how-to-install-software-in-ubuntu-charpter2.html
0:
  - 75af7c82ab27efcc1f083206929b0fc8c59bef82e3f09201c27f68632a9b274fc0421e66181c928eca798a715c7b3ccc
  - 75af7c82ab27efcc1f083206929b0fc8c59bef82e3f09201c27f68632a9b274fc0421e66181c928eca798a715c7b3ccc
1:
  - 1254c1738d4c4b956c544cc43447d2f1c59106ef05a6cbc570f0a0b3d90003fb09ce9166d5df3577da523e0afdda49d4
  - 1254c1738d4c4b956c544cc43447d2f1c59106ef05a6cbc570f0a0b3d90003fb09ce9166d5df3577da523e0afdda49d4
2:
  - ef30e17c0fd56120406459dd3c20fdfcbd4df3f982526dcfd41b73e97d919713124916827d88138afc5caff06d78a7fd
  - ef30e17c0fd56120406459dd3c20fdfcbd4df3f982526dcfd41b73e97d919713124916827d88138afc5caff06d78a7fd
comment_count:
  - 3
related_posts:
  - 'a:2:{s:4:"time";i:1224891109;s:13:"related_posts";s:1363:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/how-to-install-kde40-in-ubuntu.html" title="如何在Ubuntu 7.10下安装KDE 4.0">如何在Ubuntu 7.10下安装KDE 4.0</a></li><li><a href="http://www.digglife.cn/articles/install-compiz-fusion-and-trouble-shooting-part2-2.html" title="Ubuntu Compiz Fusion安装和常见问题解决 Part.2">Ubuntu Compiz Fusion安装和常见问题解决 Part.2</a></li><li><a href="http://www.digglife.cn/articles/install-compiz-fusion-and-trouble-shooting-part1-2.html" title="Ubuntu Compiz Fusion安装和常见问题解决 Part.1">Ubuntu Compiz Fusion安装和常见问题解决 Part.1</a></li><li><a href="http://www.digglife.cn/articles/ubuntu-easter-eggs.html" title="Ubuntu复活节彩蛋">Ubuntu复活节彩蛋</a></li><li><a href="http://www.digglife.cn/articles/make-openoffice-run-faster-in-ubuntu.html" title="加快Open Office在Ubuntu中的运行速度">加快Open Office在Ubuntu中的运行速度</a></li><li><a href="http://www.digglife.cn/articles/how-to-install-software-in-ubuntu.html" title="Ubuntu技巧:Ubuntu软件安装方法完全指南">Ubuntu技巧:Ubuntu软件安装方法完全指南</a></li><li><a href="http://www.digglife.cn/articles/top-10-google-reader-tricks.html" title="十大Google Reader使用技巧">十大Google Reader使用技巧</a></li></ul>";}'
views:
  - 15441
bot_views:
  - 2678
duoshuo_thread_id:
  - 1154125469839261871
categories:
  - Ubuntu技巧
tags:
  - ubuntu
  - 指南
  - 软件

---
<img align="right" width="202" src="https://www.digglife.net/qiniu/1413/image/fff3f031281f24295828a23dfd2e5f43.png" height="55" />可能看我博客的人有许多不知道这个续从何而来,其实我也很奇怪,为什么当时在[上一篇][1]写了一个未完待续之后就忘记了,昨天写总结突然发现这是一太监文章,所以决定今天终结它.上一篇介绍了:**1.使用新立得软件包管理器安装程序;2****.使用终端安装软件;3.****手动安装软件包中的Deb包,RPM包,桌面主题安装包和登录界面安装包.**

下面继续第三部分的内容.

<!--more-->

**1.源码包 (.tar, .tar.gz, .tgz, .tar.bz, &#8230;)**

**注:**并不是所有以.tar ,.tar.gz等为扩展名的文件都是源码压缩包,它们也有可能已经被编译过了,压缩包里面会有一个安装程序(Installer)或者扩展名为bin的可执行文件.比如Mozilla官方网站上的Firefox压缩包,Flock压缩包等.这时你需要做的只是为它们制作一个快捷方式就可以了.
  
下面介绍源码包的编译安装方式:

  * 首先解压压缩包.右键点击压缩包,选择解压到此处即可.
  * 为了编译安装软件,你必须安装有相应的编译工具.安装新立得中的软件包**Build-essential**可以获得所有的编译工具.当你确定编译工具安装正确之后,就可以打开终端程序导航到解压出的文件夹了.如果你熟悉DOS命令,这个简单的CD命令就不用介绍了.如果不熟悉,可以看[附录里面的介绍][2].
  * 进入到正确的文件夹后,运行<span style="background-color: #fffde5">./congfigure</span>命令.执行这个命令的目的有二:**检查依赖程序,创建Makefile文件**.如果命令执行失败,终端会提示安装指定的文件包,你可以在新立得中搜寻并安装.(**注意**:如果你在新立得中发现名称相同扩展名却为**.Dev的安装包**,记得也要将它打勾安装,它们是编译必须的开发工具包).同样有很多源码包并没有configure脚本,不用担心,你可以直接执行**Make命令**.
  * 编译安装的两种方法: 
      * **常规安装**:输入 <span style="background-color: #fffde5">sudo make install</span>.如果你想移除临时文件,还可以运行 <span style="background-color: #fffde5">make clean</span>.卸载程序运行 <span style="background-color: #fffde5">sudo make uninstall.</span>这两个删除命令并不时所有时候都有效,它取决于程序员是否嵌入了相关命令.
      * **软件包管理程序安装**: 如果你想以后能够在添加删除程序中轻易地卸载他们,首先安装checkinstall软件包.然后只需要运行<span style="background-color: #fffde5">sudo checkinstall</span>就可以安装源码包了.这个安装方法可能会比上面的方法用的时间更长,而且可能会需要你自己编辑该程序的某些脚本.不过好在可以在checkinstall程序里很容易的解决.

**总结:**

  * 导航到目标文件夹
  * 执行./configure
  * 执行sudo make
  * 执行sudo make install

**2.Autopackage (.package)**

这个很简单,直接导航到安装包所在的目录下,执行它即可.比如我们要安装一个位于用户digglife的桌面下的安装包test.package,直接运行 <span style="background-color: #fffde5">/home/digglife/desktop/test.package</span>即可.注意,.package文件在你的文件系统下可能没有可执行权限,需要你自己修改.如何修改,[请看附录][3].
  
**3.Klik安装包(klik:// → .cmg)**

klik是一种使用其独有网络协议klik://的在线软件储藏处.你可以直接在浏览器中点击其网站上的超链接安装软件.使用klik你必须首先使用新立得安装binutils libstdc++5 rpm gnome-about文件包,然后在终端中运行<span style="background-color: #fffde5">wget klik.atekon.de/client/install -0 -| sh</span>,下载安装Klik客户端.由于klik完全跳过了软件包管理器和文件系统,所以在安装完成后,运行这一类程序的所有东西都包含在桌面上的.cmg-file里.你可以直接双击该文件启动程序.卸载只需删除.cmg-file即可.

**4.Shell脚本安装包(.sh, .bash, &#8230;)**

安装扩展名为.sh扩展名的软件包,你可以在终端中运行sh 命令.比如我们要安装一个位于用户digglife的桌面下的安装包test.sh,只需要运行 <span style="background-color: #fffde5">sh /home/digglife/desktop/test.sh</span>即可.可能会提示权限不够,更改权限[请看附录][3].

**5.****第三方二进制安装包(.bin, &#8230;)**

我们要安装一个位于用户digglife的桌面下的安装包test.bin,你可以在终端中运行 <span style="background-color: #fffde5">/home/carl/desktop/test.bin</span>.可能会提示权限不够,更改权限[请看附录][3].

**6.附录:**

<a name="cd" title="cd"></a>**1.如何在终端中执行文件夹导航.**

终端默认所在文件夹为/home,使用pwd命令可以查看当前目录.

查看所在目录下的文件和文件夹列表,使用**<span style="background-color: #fffde5">ls</span>**命令.回到上一目录使用命令**<span style="background-color: #fffde5">cd ..</span>** .定为到下级目录使用命令cd Name,其中Name为你想进入的文件夹名称.

<a name="permissions" title="permissions"></a>**2.更改文件权限.**

右键点击该文件,选择属性,在弹出窗口中选择权限标签栏,在这里你可以修改文件的权限,Execute为可执行权限.

 [1]: https://www.digglife.net/articles/how-to-install-software-in-ubuntu.html
 [2]: #cd "cd命令"
 [3]: #permissions "permissions"
