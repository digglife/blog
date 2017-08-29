---
title: Ubuntu Compiz Fusion安装和常见问题解决 Part.1
author: 摩摩诘
type: post
date: 2007-09-10T12:09:57+00:00
url: /articles/install-compiz-fusion-and-trouble-shooting-part1-2.html
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
  - c9a2f5daf383060ccb5433055b94ef419d5749b65cafd6f82189e390940a1fa32c5b33d89d1d1ec11f30abdf280df25c
  - c9a2f5daf383060ccb5433055b94ef419d5749b65cafd6f82189e390940a1fa32c5b33d89d1d1ec11f30abdf280df25c
1:
  - 0a5ad828e841f528d03da98b43433e8c5dc27ecbba9b12aec95afc9fa6031f35d90ef4d0577f9109a978f55fda489ce5
  - 0a5ad828e841f528d03da98b43433e8c5dc27ecbba9b12aec95afc9fa6031f35d90ef4d0577f9109a978f55fda489ce5
2:
  - 817994eb043774e877c46f8bc0aea4e1b0ea8d38d1964df2e6b99dba9ec0ee2faddb2d6961012058c9c9568eecdf9089
  - 817994eb043774e877c46f8bc0aea4e1b0ea8d38d1964df2e6b99dba9ec0ee2faddb2d6961012058c9c9568eecdf9089
comment_count:
  - 3
related_posts:
  - 'a:2:{s:4:"time";i:1224892075;s:13:"related_posts";s:1504:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/install-compiz-fusion-and-trouble-shooting-part2-2.html" title="Ubuntu Compiz Fusion安装和常见问题解决 Part.2">Ubuntu Compiz Fusion安装和常见问题解决 Part.2</a></li><li><a href="http://www.digglife.cn/articles/%e5%9c%a8linux%e4%b8%8b%e4%bd%bf%e7%94%a8beryl%e5%ae%9e%e7%8e%b0vista%e6%95%88%e6%9e%9c.html" title="ubuntu 6.10 edgy beryl安装日志">ubuntu 6.10 edgy beryl安装日志</a></li><li><a href="http://www.digglife.cn/articles/add-compiz-fusion-stackswitch.html" title="Compiz Fusion新特效Stackswitch">Compiz Fusion新特效Stackswitch</a></li><li><a href="http://www.digglife.cn/articles/how-to-install-kde40-in-ubuntu.html" title="如何在Ubuntu 7.10下安装KDE 4.0">如何在Ubuntu 7.10下安装KDE 4.0</a></li><li><a href="http://www.digglife.cn/articles/how-to-install-software-in-ubuntu.html" title="Ubuntu技巧:Ubuntu软件安装方法完全指南">Ubuntu技巧:Ubuntu软件安装方法完全指南</a></li><li><a href="http://www.digglife.cn/articles/%e9%85%b7%e8%bd%af%e6%8e%a8%e8%8d%90%e8%ae%a9windows%e4%b9%9f%e7%94%a8%e4%b8%8a3d%e6%a1%8c%e9%9d%a2.html" title="酷软推荐:让windows也用上3D桌面">酷软推荐:让windows也用上3D桌面</a></li><li><a href="http://www.digglife.cn/articles/clean-up-desktop-improve-productivity-2.html" title="彻底清空桌面,让启动程序更加高效Part.2">彻底清空桌面,让启动程序更加高效Part.2</a></li></ul>";}'
views:
  - 3074
bot_views:
  - 1953
duoshuo_thread_id:
  - 1154125469839261924
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
其实暑假在家的时候就在我那台古董级电脑上安装过Compiz Fusion,不过因为显示屏的问题,实在是看不出效果,所以没有截图,并在几天之后就删除了.最近几天我的Google Reader里有关技术的国外Feed都死气沉沉,昨天到今天关于Live Translator这个微不足道的翻译工具的新闻满天飞,我估计不下看了10个不同标题相同内容的日志,实在是闷啊~所以得闲在这台电脑上重新安装.

给可能还不了解Compiz Fusion的朋友:Compiz Fusion是刚刚推出不久的梦幻级桌面特效程序,它继承了<a title="beryl相关日志" href="https://www.digglife.net/articles/tag/beryl" target="_blank">Beryl</a>和Compiz各自的优良传统,并在特效和性能方面有了极大的提升.有兴趣的可以看看我很早之前<a title="Ubuntu Compiz Fusion特效演示视频" href="http://www.tudou.com/programs/view/xCk_J6E-XcE/" target="_blank">上传到土豆的视频</a>.

[![compiz-fusion-cube.png][1]][2]

下面的安装方法基本来自<a title="compiz fusion安装指南" href="http://forum.ubuntu.org.cn/viewtopic.php?t=61686" target="_blank">Ubuntu社区论坛</a>,但是我在这台电脑的安装过程中出了一些问题,好在都想到办法解决了.

<!--more-->

<span style="font-size: medium;">一.安装.</span>

**1.安装显卡驱动.**

如果是新装的Ubuntu,还没有安装显卡驱动,可以先到<span style="background-color: #ffcc99">系统&#8211;系统管理&#8211;受限驱动管理器</span>中启用受限制的驱动.注:我使用的是NVIDIA GeForce 5200显卡.

**2.添加密钥和软件源.**

因为官方源里面还没有Compiz Fusion,所以需要添加第三方软件源,来自http://download.tuxfamily.org.

获得密钥:

sudo wget http://download.tuxfamily.org/3v1deb/DD800CD9.gpg -O- | sudo apt-key add &#8211;

添加软件源:

sudo gedit /etc/apt/sources.list

在弹出的软件源文本中加入以下两条:

deb http://download.tuxfamily.org/3v1deb feisty eyecandy
  
deb-src http://download.tuxfamily.org/3v1deb feisty eyecandy

保存后更新:

sudo apt-get update
  
sudo apt-get dist-upgrade

**3.下载安装Compiz和Compiz Fusion**

sudo apt-get install compiz compiz-gnome
  
sudo apt-get install compizconfig-settings-manager
  
sudo apt-get install compiz-fusion-*

**4.故障解决** 

<span style="color: #ff0000;"><strong>问题#1.</strong></span>

据我自己的经验,如果在终端里使用以上命令进行下载,速度将会极为缓慢(校园网连接国外的网站那叫一个慢),另外,我还看到有好多朋友都无法获取密钥,所以我们可以直接到原始网站使用下载工具进行下载.下面是我根据终端里的提示和新利得中的记录研究出来的Deb包列表和下载地址(注意:因为有依赖关系问题,所以请按顺序安装):

**Compiz系:**

  * <a title="compiz-core" href="http://download.tuxfamily.org/3v1deb/pool/feisty/eyecandy/compiz-core_0.5.5~git20070905+3v1ubuntu0_i386.deb" target="_blank">compiz core</a>
  * <a title="compiz-plugins" href="http://download.tuxfamily.org/3v1deb/pool/feisty/eyecandy/compiz-plugins_0.5.5~git20070905+3v1ubuntu0_i386.deb" target="_blank">compiz plugins</a>
  * [libdecoration][3]
  * <a title="compiz-all" href="http://download.tuxfamily.org/3v1deb/pool/feisty/eyecandy/compiz_0.5.5~git20070905+3v1ubuntu0_all.deb" target="_blank">compiz</a>
  * <a href="http://download.tuxfamily.org/3v1deb/pool/feisty/eyecandy/compiz-gnome_0.5.5~git20070905+3v1ubuntu0_i386.deb" target="_blank">compiz gnome</a>
  * <a href="http://download.tuxfamily.org/3v1deb/pool/feisty/eyecandy/libcompizconfig0_0.5.2~git20070904+3v1ubuntu0_i386.deb" target="_blank">libcompizconfig </a>
  * <a href="http://download.tuxfamily.org/3v1deb/pool/feisty/eyecandy/python-compizconfig_0.5.2~git20070903+3v1ubuntu0_i386.deb" target="_blank">python compizconfig</a>
  * <a title="compizconfig settings manager" href="http://download.tuxfamily.org/3v1deb/pool/feisty/eyecandy/compizconfig-settings-manager_0.6.99~git20070905+3v1ubuntu0_i386.deb" target="_blank">compizconfig settings manager</a>

**Fusion插件系:**

  * <a href="http://download.tuxfamily.org/3v1deb/pool/feisty/eyecandy/compiz-fusion-plugins-main_0.5.2~git20070905+3v1ubuntu0_i386.deb" target="_blank">compiz fusion plugins main</a>
  * <a href="http://download.tuxfamily.org/3v1deb/pool/feisty/eyecandy/compiz-fusion-plugins-extra_0.5.2~git20070905+3v1ubuntu0_i386.deb" target="_blank">compiz fusion plugins extra</a>
  * <a href="http://download.tuxfamily.org/3v1deb/pool/feisty/eyecandy/compiz-fusion-plugins-unofficial_0.0.2~git20070902+3v1ubuntu0_i386.deb" target="_blank">compiz fusion plugins unofficial</a>
  * <a href="http://download.tuxfamily.org/3v1deb/pool/feisty/eyecandy/compiz-fusion-plugins-unsupported_0.5.2~git20070905+3v1ubuntu0_i386.deb" target="_blank">compiz fusion plugins unsupported</a>

<span style="color: #ff0000;"><strong>#问题2:</strong></span>

有些同学在执行 sudo apt-get install compiz compiz-gnome的时候出现以下错误:

> <span class="postbody">正预备替换 compiz-gnome 1:0.3.6-1ubuntu13 (使用 &#8230;/compiz-gnome_1%3a0.5.1+git20070627~3v1ubuntu1_i386.deb) &#8230; 正在解压缩将用于更替的包文件 compiz-gnome &#8230;<br /> dpkg：处理 /var/cache/apt/archives/compiz-gnome_1%3a0.5.1+git20070627~3v1ubuntu1_i386.deb (&#8211;unpack)时出错：<br /> 正试图覆盖“/usr/lib/compiz/libgconf.so”，它属于软件包 compiz-plugins<br /> 在处理时有错误发生：<br /> /var/cache/apt/archives/compiz-gnome_1%3a0.5.1+git20070627~3v1ubuntu1_i386.deb<br /> E: Sub-process /usr/bin/dpkg returned an error code (1)</span>

或者出现以下提示:

> 下列的软件包有不能满足的依赖关系：
  
> compiz: 依赖: compiz-decorator 但却无法安装它
  
> E: 无法安装的软件包
  
> aro@aro-laptop:~$

其实我在安装的时候也出现了第一个错误,这两个错误都和软件包依赖有关,上面的这些命令我觉得并不怎么完善,**具体解决方法如下**:

  * 定位到<span style="background-color: #ffcc99">系统&#8211;系统管理&#8211;新利得软件包管理器</span>,打开后在左边栏找到&#8221;已损坏&#8221;,卸载损坏的安装包(实际就是删除原有的compiz),退出.
  * 下载安装#问题1中提到的compiz core,compiz plugin和libdecoration三个文件.
  * 重新执行<span style="background-color: #ffcc99">sudo apt-get install compiz compiz-gnome</span>,或者如果你愿意可以直接依次下载上面的所有deb包安装(个人推荐).

<span style="color: #ff0000;"><strong>问题#3</strong></span>

使用ATi显卡的朋友可能会出现以下问题:

> <span class="postbody">Fatal: Failed test: texture_from_pixmap support<br /> Checks indicate that it’s impossible to start compiz on your system.</span>

这个问题我无从实践,因为这台电脑是NVIDIA的显卡,不过我在Ubuntu英文论坛上看到了解决方案.问题的关键在于要安装XGL,因为安装步骤很多,我又无法实践,所以有这个问题的请参见:<a title="ATI显卡如何安装XGL+compiz fusion" href="http://ubuntuforums.org/showthread.php?t=488385" target="_blank">How To : Compiz Fusion for ATI cards + Xgl in Feisty</a>,里面有非常详细的说明,尽管是英文,但是只需复制代码即可,所以不是障碍.

### 二.简单的使用指南

以上安装完成之后,你就可以启动Compiz Fusion了.同时按下<span style="background-color: #ffcc99">Alt+F2</span>,输入<span style="background-color: #ffcc99">compiz &#8211;replace</span>即可启动.默认状态下已经有不少有趣的效果.

定位到<span style="background-color: #ffcc99">系统&#8211;首选项&#8211;CompizConfig Settings Manager</span>,打开后可以对效果进行自定义.一般大家在视频里看到的水族馆效果,火焰字,类Vista的层叠(Flip)效果在默认状态下是没有开启的,需要你自己勾选对应的复选框.

**立方体效果:**同时按下<span style="background-color: #ffcc99">ctrl+Alt+鼠标左键(Button 1)</span>.这个和Beryl下是一样的.

**火焰字:**在左侧类别栏目的Effect下,勾选&#8221;在屏幕上绘制火焰&#8221;.同时按下<span style="background-color: #ffcc99">Shift+Win(Super)+B1</span>,退出火焰字同时按下<span style="background-color: #ffcc99">Shift+Win+C</span>.

**层叠效果:**在左侧类别栏目的Windows Management下,勾选Shift-Switcher.<span style="background-color: #ffcc99">Win+Tab</span>(和Vista下一样).

**桌面缩放:**<span style="background-color: #ffcc99">Win+鼠标滚轮</span> .

**屏幕飞雪:**在左侧类别栏目的Extra下勾选飞雪.同时按下<span style="background-color: #ffcc99">Win+F3.</span>

还有很多效果,可以到Manager中慢慢研究,只要点击右边的对应效果就可以对它进行快捷键,效果微调等方面的自定义.

[<img src="http://digglife.qiniudn.com/wp-content/uploads/3/379/2007/09/flip-snow.png" alt="Vista层叠和雪花效果" width="450" height="360" />][4]

[![火焰字][5]][6]

**注意:**尽管Compiz Fusion和Beryl相比在性能上大有提升,但是开启太多效果后还是会造成系统速度变慢,所以有些很无聊的效果还是看看就算吧.有些同学说开启之后X还变快了,呃,很显然那是不可能的&#8230;.

待续&#8230;.

 [1]: http://digglife.qiniudn.com/wp-content/uploads/3/379/2007/09/compiz-fusion-cube.thumbnail.png
 [2]: https://www.digglife.net/wp-content/uploads/3/379/2007/09/compiz-fusion-cube.png "compiz-fusion-cube.png"
 [3]: http://download.tuxfamily.org/3v1deb/pool/feisty/eyecandy/libdecoration0-dev_0.5.5~git20070905+3v1ubuntu0_i386.deb "compiz-decorator"
 [4]: https://www.digglife.net/wp-content/uploads/3/379/2007/09/flip-snow.png "flip-snow.png"
 [5]: http://digglife.qiniudn.com/wp-content/uploads/3/379/2007/09/flame.thumbnail.png
 [6]: https://www.digglife.net/wp-content/uploads/3/379/2007/09/flame.png "火焰字"