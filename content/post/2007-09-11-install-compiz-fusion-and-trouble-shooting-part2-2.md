---
title: Ubuntu Compiz Fusion安装和常见问题解决 Part.2
author: 摩摩诘
type: post
date: 2007-09-11T14:41:08+00:00
url: /articles/install-compiz-fusion-and-trouble-shooting-part2-2.html
ratings_users:
  - 0
  - 0
ratings_score:
  - 0
  - 0
ratings_average:
  - 0
  - 0
0:
  - c0a2cbfb4c7bd7928926dde094e2432aa5a607e977e2687f5e5503b013925578f4ad6340f6fc4d6a93db44d6751a1eae
  - c0a2cbfb4c7bd7928926dde094e2432aa5a607e977e2687f5e5503b013925578f4ad6340f6fc4d6a93db44d6751a1eae
1:
  - 6229ce8b8521a2c6e2e6f2e8b4a4e3bea94ba6d55ad08da742d9ad999639b18ded8da4af03ae5d63976421c374aedac7
  - 6229ce8b8521a2c6e2e6f2e8b4a4e3bea94ba6d55ad08da742d9ad999639b18ded8da4af03ae5d63976421c374aedac7
2:
  - baa12ef157c92759cb7fc68c3e16a2affcbeed4faac8d29337f5f4a2a7a432c7f4ff9a54dc61720b6648d5d697892dd3
  - baa12ef157c92759cb7fc68c3e16a2affcbeed4faac8d29337f5f4a2a7a432c7f4ff9a54dc61720b6648d5d697892dd3
comment_count:
  - 3
related_posts:
  - 'a:2:{s:4:"time";i:1224892075;s:13:"related_posts";s:1504:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/install-compiz-fusion-and-trouble-shooting-part1-2.html" title="Ubuntu Compiz Fusion安装和常见问题解决 Part.1">Ubuntu Compiz Fusion安装和常见问题解决 Part.1</a></li><li><a href="http://www.digglife.cn/articles/%e5%9c%a8linux%e4%b8%8b%e4%bd%bf%e7%94%a8beryl%e5%ae%9e%e7%8e%b0vista%e6%95%88%e6%9e%9c.html" title="ubuntu 6.10 edgy beryl安装日志">ubuntu 6.10 edgy beryl安装日志</a></li><li><a href="http://www.digglife.cn/articles/add-compiz-fusion-stackswitch.html" title="Compiz Fusion新特效Stackswitch">Compiz Fusion新特效Stackswitch</a></li><li><a href="http://www.digglife.cn/articles/how-to-install-kde40-in-ubuntu.html" title="如何在Ubuntu 7.10下安装KDE 4.0">如何在Ubuntu 7.10下安装KDE 4.0</a></li><li><a href="http://www.digglife.cn/articles/how-to-install-software-in-ubuntu.html" title="Ubuntu技巧:Ubuntu软件安装方法完全指南">Ubuntu技巧:Ubuntu软件安装方法完全指南</a></li><li><a href="http://www.digglife.cn/articles/%e9%85%b7%e8%bd%af%e6%8e%a8%e8%8d%90%e8%ae%a9windows%e4%b9%9f%e7%94%a8%e4%b8%8a3d%e6%a1%8c%e9%9d%a2.html" title="酷软推荐:让windows也用上3D桌面">酷软推荐:让windows也用上3D桌面</a></li><li><a href="http://www.digglife.cn/articles/clean-up-desktop-improve-productivity-2.html" title="彻底清空桌面,让启动程序更加高效Part.2">彻底清空桌面,让启动程序更加高效Part.2</a></li></ul>";}'
views:
  - 3141
bot_views:
  - 2191
duoshuo_thread_id:
  - 1154125469839261925
categories:
  - Ubuntu技巧
tags:
  - beryl
  - compiz fusion
  - ubuntu
  - 安装
  - 桌面
  - 特效
  - 问题

---
<a href="https://www.digglife.net/articles/install-compiz-fusion-and-trouble-shooting-part1-2.html" title="Ubuntu Compiz Fusion安装和常见问题解决 Part.1" target="_blank">Ubuntu Compiz Fusion安装和常见问题解决 Part.1</a>中我重点说明了我在安装过程中的故障解决和特效的简单使用.下面主要是compiz fusion的优化,包括主题的安装和系统托盘管理的安装,Avant Window Navigator的安装,另附一些问题解决方案.

### 三.Compiz Fusion系统托盘管理图标的安装

[![compiz fusion系统托盘图标][1]][2]

<!--more-->

为了更加方便地管理compiz fusion，我们最好下载安装一个compiz fusion icon,这样就可以随时在系统托盘更改显示效果了.具体安装方法如下:

**1.在终端中执行以下命令**.

这个命令的目的是下载Git协议(具体含义可以参考Ubuntu软件安装指南)支持软件包和compiz开发包.

 <span class="postbody">sudo apt-get install git git-core compiz-dev </span>

**2. 下载compiz-ico软件包**

 <span class="postbody">git-clone <a href="git://anongit.opencompositing.org/users/crdlb/fusion-icon" target="_blank">git://anongit.opencompositing.org/users/crdlb/fusion-icon</a> </span>

注：如果无法下载,可以考虑直接下载我上传的[fusion-icon安装包][3](.zip 140KB).下载后解压到<span style="background-color: #ffcc99">主文件夹</span>继续下面的步骤即可。[][3]

**3.安装compiz-ico**

按顺序执行以下命令：

<span class="postbody">cd fusion-icon<br /> make<br /> sudo make install </span>

**4.启动和使用**

安装完毕后在主菜单的系统工具下可以找到compiz fusion icon启动即可.如果你希望在进入系统时自动启动可以<span style="background-color: #ffcc99">系统&#8211;首选项&#8211;会话</span>,新建一个新会话,填入<span class="postbody"></span><span style="background-color: #ffcc99">fusion-icon</span>就可以了.

右键点击系统托盘中的fusion图标，选择select windows decorator.然后选择emerald即可启用emerald主题.这样的主题可以在<a href="http://www.gnome-look.org/" title="emerald主题下载" target="_blank">gnome-look</a>中下载到.比如<a href="https://www.digglife.net/wp-content/uploads/3/379/2007/09/emerald-osx.zip" title="模拟OSX的emerald主题" target="_blank">模拟Mac OSX的emerald主题</a>,当然,这个主题需要和Gnome的OSX主题配合使用才能达到最佳效果,Gnome主题同样可以在上面提到的gnome-look下载到.

### 四.Avant Window Navigator的安装和使用.

AWN并不是Compiz Fusion的组件,不过我推荐安装了Compiz Fusion的的朋友使用.这是一个类似于OSX下Dock的程序,基本上能够达到以假乱真的效果.其实主要不是为了放Mac,而是这个Dock的确能够加快操作效率,并保证桌面的整洁.

[![avant window navigator][4]][5]

至于安装,很多地方都是介绍<a href="http://awn.wetpaint.com/page/Ubuntu+Feisty+Repository?t=anon" title="AWN常规安装方法" target="_blank">使用命令行添加源和密钥,然后下载安装</a>.不过我觉得既然我们能够使用工具下载这些文件(我使用终端下载的时候经常连接超时),为什么不直接像在Windows下面那样双击即安装呢?所以我直接贴出需要安装的软件包地址,大家按顺序安装即可.avant window navigator不久前刚刚升级,下面是最新版本的下载地址 .

<a href="http://download.tuxfamily.org/syzygy42/pool/feisty/avant-window-navigator/avant-window-navigator-bzr_0.1.2-bzr94-1.tar.gz" title="AWN主文件下载" target="_blank">Avant Window Navigator(主文件)</a>

<a href="http://download.tuxfamily.org/syzygy42/pool/feisty/avant-window-navigator/awn-core-applets-bzr_0.1.0-bzr43-1_i386.deb" title="AWN的小组件下载" target="_blank">Avant Core Applets(一些有趣的小组件)</a>

安装完毕后同时按下<span style="background-color: #ffcc99">Alt+F2</span>,输入<span style="background-color: #ffcc99">avant windows navigator</span>即可启动.管理工具在<span style="background-color: #ffcc99">系统&#8211;首选项&#8211;AWN Manager</span>.

如果你希望它开机启动,可以和上面设置fusion-icon一样,新建一个会话,在窗口中填入avant windows navigator即可.

默认状态下AWN的底色是黑色,可能你会觉得不太好看,这里有一款[Glass Beach主题][6]可以下载,效果如上面的截图.下载解压后使用AWN Manager导入即可,具体安装方法内详.

AWN相比早前版本的更新(8月26日更新的,也不能算新了,呵呵)包括:

  * 改进的管理页面.
  * 新增主题更改功能.
  * 页面预览功能.

[![程序预览][7]][8]

  * 文件夹抽屉导航.(不支持中文名文件夹显示,黑体的那个小写e谁能给解决一下?)

[![文件夹抽屉][9]][10]

[![AWN主菜单][11]][12]

[][10]

**注意:**如果你在Compiz Fusion(或者Beryl)没有启用的状态下打开AWN,那么它所在的区域会有一大块黑色.

关于compiz fusion的安装我所了解的就这么多了,这篇日志可能会不断更新.如有更新我会在以后的日志中提到,所以如果有兴趣看看的话,不妨<a href="http://feed.digglife.cn" title="订阅digglife" target="_blank">订阅DiggLife</a>. 8)

 [1]: https://www.digglife.net/wp-content/uploads/3/379/2007/09/compiz-fusion-tray-icon.png
 [2]: https://www.digglife.net/wp-content/uploads/3/379/2007/09/compiz-fusion-tray-icon.png "compiz fusion系统托盘图标"
 [3]: https://www.digglife.net/wp-content/uploads/3/379/2007/09/fusion-icon.zip "fusion-icon安装包"
 [4]: https://www.digglife.net/wp-content/uploads/3/379/2007/09/awn.thumbnail.png
 [5]: https://www.digglife.net/wp-content/uploads/3/379/2007/09/awn.png "avant window navigator"
 [6]: https://www.digglife.net/wp-content/uploads/3/379/2007/09/glass-beach-theme.zip "AWN Glass Beach主题"
 [7]: https://www.digglife.net/wp-content/uploads/3/379/2007/09/preview1.png
 [8]: https://www.digglife.net/wp-content/uploads/3/379/2007/09/preview1.png "程序预览"
 [9]: https://www.digglife.net/wp-content/uploads/3/379/2007/09/stack.thumbnail.png
 [10]: https://www.digglife.net/wp-content/uploads/3/379/2007/09/stack.png "文件夹抽屉"
 [11]: https://www.digglife.net/wp-content/uploads/3/379/2007/09/awn-main-menu.thumbnail.png
 [12]: https://www.digglife.net/wp-content/uploads/3/379/2007/09/awn-main-menu.png "AWN主菜单"
