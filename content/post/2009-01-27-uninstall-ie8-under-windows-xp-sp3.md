---
title: 辟谣:Windows XP SP3安装IE8 RC1后可以卸载
author: 摩摩诘
type: post
date: 2009-01-27T11:02:17+00:00
url: /articles/uninstall-ie8-under-windows-xp-sp3.html
index_image:
  - https://www.digglife.net/wp-content/uploads/IndexImage/ie8.jpg
bot_views:
  - 2363
views:
  - 2516
duoshuo_thread_id:
  - 1154125469839262131
categories:
  - Windows技巧
tags:
  - IE
  - ie8
  - windows

---
IE 8 RC1今天发布之后有传言说<a rel="nofollow" href="http://cnbeta.com/articles/75733.htm" target="_blank">Windows XP SP3用户安装之后将不可卸载</a>,我想发布这条消息的人是看了<a title="IE官方博客" href="http://blogs.msdn.com/ie/" target="_blank">IE官方博客</a>的,只可惜断章取义,没有仔细看清楚关于Windows XP SP3的说明.事实是:**只要你没有在升级到Windows XP SP3之前安装过[IE8的Beta版][1],那么,安装IE8 RC1之后是可以通过&#8221;添加删除程序&#8221;卸载的.**

微软产品博客的文风大部分如此,事无巨细,用词考究,在问题说明上讲求无微不至,所以导致行文上有点绕弯子,但是大部分时候都是考虑周全的表现.具体体现在这次IE 8 RC1的安装问题上就是,各个平台的情况都有详细的说明,关于Windows XP SP3的安装尤为绕口,下面看看IE团队的朋友们到底是什么意思.

<!--more-->

对于Windows XP SP3用户:

只有<span style="background-color:#f5a000;">当你在安装IE8 Beta版之后才安装Windows XP SP3</span>,我们才建议首先手动删除IE8 Beta版本,然后升级到IE8 RC1.

> The only time we encourage you to manually uninstall Internet Explorer 8 Beta versions prior to upgrading to IE8 RC1 is if you happened to install Windows XP SP3 after installing IE8 Beta.

检查以下两点,看你是否需要首先手动卸载IE8 Beta版:

  * 你的电脑运行的是不是Windows XP SP3
  * &#8220;添加删除程序&#8221;中IE 8 Beta的卸载按钮是否为灰色

如果两个问题的回答都是肯定的,那么你在安装IE8 RC1之后将无法卸载IE8,也无法卸载Windows XP SP3.安装向导将会在安装的时候弹出如下警告:

![dialog box asking ][2]

如果你选择继续,那么Windows XP SP3和IE8 RC1将无法卸载.你依然可以升级到IE8以后的版本,但是你将无法卸载它们.

为了避免这种情况发生,我们强烈建议你在安装IE8 RC1之前,按照一下步骤操作:

  1. 卸载Windows XP SP3
  2. 卸载 IE8 Beta
  3. 重新安装Windows XP SP3
  4. 安装IE8 RC1

<span style="background-color:#f5a000;">上面来自IE官方博客,略有精简.这些话简单说来就是:</span>

**如果你在升级到Windows XP SP3之前就安装了IE8 Beta版本,而又没有事先手动卸载IE8 Beta1,那么安装IE8 RC1之后,Windows XP SP3和IE8 RC1将都无法卸载.**

其实这种情况应该很少,因为我记得IE8 Beta出现之前Windows XP SP3就已经发布,想必大部分朋友都是在Windows XP SP3下安装的IE8 Beta,而在升级到Windows XP SP3之后没有安装过IE8的朋友就完全不需要担心了.IE团队说这么多只是为了将所有的情况都说明清楚,免得到时候有人埋怨罢了.

我这个标题起得也不算周全,但是至少要比所谓的&#8221;Windows XP SP3用户安装IE8后将不可逆&#8221;这种误解要靠谱得多.

 [1]: https://www.digglife.net/articles/ie8-new-features-download.html "IE 8 Beta 1简体中文版下载和新功能介绍| DiggLife"
 [2]: https://www.digglife.net/qiniu/2892/image/f76514b5b537bae6c126c4f43ae7354f.jpg
