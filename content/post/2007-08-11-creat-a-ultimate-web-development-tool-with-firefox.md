---
title: 让Firefox变成终极网页设计工具
author: 摩摩诘
type: post
date: 2007-08-11T08:09:11+00:00
url: /articles/creat-a-ultimate-web-development-tool-with-firefox.html
0:
  - dc91ea8397d73c08a25285e7878ec9a1cff03db15e13bbb405d92c493a5c85d282c660fec83b0b716ebd81ed87c4ca2b
  - dc91ea8397d73c08a25285e7878ec9a1cff03db15e13bbb405d92c493a5c85d282c660fec83b0b716ebd81ed87c4ca2b
1:
  - 380d608027652155543991ee3222b9cefdbbf91cbfc991a57d251ad7dfde83afa43920b34558ff41cd63bec07d0ef667
  - 380d608027652155543991ee3222b9cefdbbf91cbfc991a57d251ad7dfde83afa43920b34558ff41cd63bec07d0ef667
2:
  - bd1f2f44b12d49bbeb0ee0be56f31c968be2f5eaae232212e8c7709999da41b0f56fb69da3d18e49af751a2995a4788f
  - bd1f2f44b12d49bbeb0ee0be56f31c968be2f5eaae232212e8c7709999da41b0f56fb69da3d18e49af751a2995a4788f
3:
  - 883a036abd082fd4429823d6a450fbf2df3b75eda04a0586ae86f9964b7ae46c7e99b8044a4a031b9453b55dba6045cf
  - 883a036abd082fd4429823d6a450fbf2df3b75eda04a0586ae86f9964b7ae46c7e99b8044a4a031b9453b55dba6045cf
comment_count:
  - 5
trackback_count:
  - 2
related_posts:
  - 'a:2:{s:4:"time";i:1224882355;s:13:"related_posts";s:1227:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/firefox-addons-weekly-issue3.html" title="一周Firefox扩展推荐-第三辑">一周Firefox扩展推荐-第三辑</a></li><li><a href="http://www.digglife.cn/articles/firefox-addons-weekly-issue2.html" title="一周Firefox扩展推荐-第二辑">一周Firefox扩展推荐-第二辑</a></li><li><a href="http://www.digglife.cn/articles/firefox-addons-weekly-issue1.html" title="一周Firefox扩展推荐-第一辑">一周Firefox扩展推荐-第一辑</a></li><li><a href="http://www.digglife.cn/articles/social-web-firefox-yoono.html" title="社会化浏览器扩展Yoono">社会化浏览器扩展Yoono</a></li><li><a href="http://www.digglife.cn/articles/add-google-toolbar-functions-firefox3.html" title="给Firefox 3添加Google Toolbar的功能">给Firefox 3添加Google Toolbar的功能</a></li><li><a href="http://www.digglife.cn/articles/firefox-addons-new-site.html" title="Firefox 3附加软件页面预览">Firefox 3附加软件页面预览</a></li><li><a href="http://www.digglife.cn/articles/firefox-universal-uploader.html" title="Firefox:全能上传扩展FireUploader">Firefox:全能上传扩展FireUploader</a></li></ul>";}'
views:
  - 6320
bot_views:
  - 2930
duoshuo_thread_id:
  - 1154125469839261883
categories:
  - 火狐技巧
tags:
  - 扩展
  - 网页设计

---
通过适当的配置,<a target="_blank" href="https://www.digglife.net/articles/category/firefox/">Firefox</a>可以变成一个超级网页设计工具,<a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/08/webdev.png"><img align="right" width="250" src="https://www.digglife.net/wp-content/uploads/3/379/2007/08/webdev-thumb.png" alt="webdev" height="35" /></a>让你能够实时设计网页样式,测试Javascript以及编辑HTMl文件.我们只需要安装以下扩展就可以实现丰富多样的网页编辑功能.  

<!--more-->

**重要:**因为我们平时用不到这些扩展,所以最好建立一个独立的Firefox配置文件,这样就不会影响到常规使用时的速度了.

**一.创建一个独立的Firefox配置文件.**

创建多个配置文件的好处在于可以打造多个为某个目的专用的Firefox,同时也适合于多用户共享电脑,所以下面的方法不仅限于本文的目的.

1.开始&#8211;运行,输入 <font color="#ff5a00" face="Courier New">firefox.exe -profilemanager</font>,启动Firefox用户配置文件向导.如果你的Firefox并未安装在默认目录下,这条命令应改为 <font color="#ff5a00" face="Courier New">firefox所在路径\firefox.exe -profilemanager</font>.

2.点击创建配置文件,创建一个新用户,并为该用户取一个你自己喜欢的名字.创建后退出.如图所示,我的新建用户为Webdev(Web Development).

<a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/08/creat-profile.png"><img width="367" src="https://www.digglife.net/wp-content/uploads/3/379/2007/08/creat-profile-thumb.png" alt="creat_profile" height="267" /></a>

3.为新配置文件创建图标.复制桌面上的Firefox图标,并直接粘贴在桌面上,右键点击该图标,选择属性,在目标一栏的文字后面添加:

<font color="#ff5a00" face="Courier New">-P PROFILENAME -no-remote</font>

其中PROFILENAME为你自己设定的配置文件名称. <font face="Courier New">-no-remote</font>是为了能够让不同配置文件的Firefox同时运行.

<a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/08/properties.png"><img width="367" src="https://www.digglife.net/wp-content/uploads/3/379/2007/08/properties-thumb.png" alt="properties" height="200" /></a>  

这样,这个名为Webdev配置文件就能独立于原来的那个之外使用了,所有的配置,包括扩展,书签,主题都是全新的.

**二.必备的网页设计扩展**

**1.**<a target="_blank" href="http://www.joehewitt.com/software/firebug/"><strong>FireBug</strong></a>

Firebug是测试Javascript,查看CSS和HTML的绝佳工具.你可以在修改代码后立即测试页面的变化.

<a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/08/firebug.png"><img width="450" src="https://www.digglife.net/wp-content/uploads/3/379/2007/08/firebug-thumb.png" alt="firebug" height="171" /></a>

<a target="_blank" href="http://www.getfirebug.com/releases/firebug1.0-current.xpi">点击下载</a>  

**2.**[**Web Developer Extension**][1]

这个扩展是我最早听说也是最常用的一个网页设计扩展,当时修改模板的时候起了很大作用.它几乎囊括了网页设计的所有元素,主要作用在于监测和查看代码.

<a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/08/web-developer.png"><img width="345" src="https://www.digglife.net/wp-content/uploads/3/379/2007/08/web-developer-thumb.png" alt="Web_developer" height="25" /></a>

<a target="_blank" href="http://downloads.chrispederick.com/work/web-developer/web-developer.xpi">点击下载</a>

**3.**[**Aardvark Extension**][2]

这个轻量级扩展可以简单地显示网页元素的Class和ID,当你只想快速获得某个元素的信息时非常有用,你还可以通过它移除网页上的元素.

<a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/08/aardvark.png"><img width="225" src="https://www.digglife.net/wp-content/uploads/3/379/2007/08/aardvark-thumb.png" alt="Aardvark" height="55" /></a>

<a target="_blank" href="http://karmatics.com/aardvark/aardvark.xpi">点击下载</a>

**4.**[**Colorzilla**][3] ****

直接从网页上获取色彩代码和RGB信息,相当于图像编辑软件里的拾色器.

**<a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/08/colorzilla.png"><img width="390" src="https://www.digglife.net/wp-content/uploads/3/379/2007/08/colorzilla-thumb.png" alt="colorzilla" height="64" /></a>** 

<a target="_blank" href="http://www.iosart.com/firefox/colorzilla/ColorZilla_1.0.xpi">点击下载</a>

**5.**[**View Source With**][4]

使用多种外部软件查看网页代码.

<a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/08/view-source-with.png"><img width="385" src="https://www.digglife.net/wp-content/uploads/3/379/2007/08/view-source-with-thumb.png" alt="View_source_with" height="120" /></a>

<a target="_blank" href="https://addons.mozilla.org/en-US/firefox/downloads/file/15007/viewsourcewith-0.0.9-fx+mz+tb+nvu+ns+sm+fl.xpi">点击下载</a>

**6.**[**HTML Validator**][5]

快速验证HTML代码的合法性.

<a target="_blank" href="http://htmlvalidator.sourceforge.net/mozilla/tidy_firefox_win_0840.xpi">Windows平台下载</a>

<a target="_blank" href="http://htmlvalidator.sourceforge.net/mozilla/tidy_firefox_linux_0840.xpi">Linux平台下载</a>

**7.**[**Measure It**][6]

距离测量工具.

<a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/08/meanure.png"><img width="370" src="https://www.digglife.net/wp-content/uploads/3/379/2007/08/meanure-thumb.png" alt="meanure" height="75" /></a>

<a target="_blank" href="http://www.kevinfreitas.net/extensions/measureit/measureit.xpi">点击下载</a>

**8.**[**IE View**][7]** /** [**IE Tab**][8]** /** [**OperaView**][9]** /** [**FirefoxView**][10]** /** [**Safari View**][11]** /** [**IE View Lite**][12]

在Firefox中调用其他浏览器渲染网页.测试网页的兼容性时很有用.

<a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/08/ietab.png"><img width="220" src="https://www.digglife.net/wp-content/uploads/3/379/2007/08/ietab-thumb.png" alt="ietab" height="110" /></a>

**9.**[**Clear Cache Button**][13]

清除网页缓存,检查CSS更改时非常有用.

<a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/08/cleancache.png"><img width="110" src="https://www.digglife.net/wp-content/uploads/3/379/2007/08/cleancache-thumb.png" alt="cleancache" height="65" /></a>

<a target="_blank" href="https://addons.mozilla.org/en-US/firefox/downloads/file/7326/clear_cache_button-0.5-fx.xpi">点击下载</a>

**10.**[**Restart Firefox**][14] ****

在不损坏当前标签和进程的情况下重启Firefox.

<a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/08/restart-firefox.png"><img width="210" src="https://www.digglife.net/wp-content/uploads/3/379/2007/08/restart-firefox-thumb.png" alt="restart_firefox" height="95" /></a>

<a target="_blank" href="https://addons.mozilla.org/en-US/firefox/downloads/file/5525/restart_firefox-0.3-fx.xpi">点击下载</a>

**11.**[**Tab Mix Plus**][15]

尽管这是一个常规扩展,但是复制标签和复制标签链接功能对网页设计很有作用.

<a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/08/tabmix.png"><img src="https://www.digglife.net/wp-content/uploads/3/379/2007/08/tabmix-thumb.png" alt="tabmix" /></a>

<a target="_blank" href="https://addons.mozilla.org/en-US/firefox/downloads/file/16566/tab_mix_plus-0.3.6-fx.xpi">点击下载</a>

**12.**[**YSlow**][16]

Yslow是雅虎新近出品的一个网页分析工具.它能够给你提供网页错误信息以及网页优化建议.必须安装Firebug后才能使用该扩展.

<a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/08/yslow.png"><img width="450" src="https://www.digglife.net/wp-content/uploads/3/379/2007/08/yslow-thumb.png" alt="yslow" height="360" /></a>

<a target="_blank" href="https://addons.mozilla.org/en-US/firefox/downloads/file/18173/yslow-0.7.1-fx.xpi">点击下载</a>

 [1]: http://chrispederick.com/work/webdeveloper/
 [2]: http://www.karmatics.com/aardvark/
 [3]: http://www.iosart.com/firefox/colorzilla/index.html
 [4]: https://addons.mozilla.org/en-US/firefox/addon/394
 [5]: http://users.skynet.be/mgueury/mozilla/
 [6]: http://www.kevinfreitas.net/extensions/measureit/
 [7]: http://ieview.mozdev.org/
 [8]: https://addons.mozilla.org/extensions/moreinfo.php?id=1419
 [9]: https://addons.mozilla.org/en-US/firefox/addon/1190
 [10]: https://addons.mozilla.org/en-US/firefox/addon/223
 [11]: https://addons.mozilla.org/en-US/firefox/addon/4641
 [12]: https://addons.mozilla.org/en-US/firefox/addon/1429
 [13]: https://addons.mozilla.org/extensions/moreinfo.php?id=1801&application=firefox
 [14]: https://addons.mozilla.org/en-US/firefox/addon/1249
 [15]: https://addons.mozilla.org/en-US/firefox/addon/1122
 [16]: http://developer.yahoo.com/yslow/
