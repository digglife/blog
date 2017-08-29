---
title: 完美解决Firefox下日文字体显示为宋体的问题
author: 摩摩诘
type: post
date: 2008-07-11T11:26:53+00:00
url: /articles/japanese-font-firefox.html
comment_count:
  - 7
related_posts:
  - 'a:2:{s:4:"time";i:1224887524;s:13:"related_posts";s:1313:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/vista-theme-visual-style-download.html" title="7个漂亮的Vista主题(视觉样式)下载">7个漂亮的Vista主题(视觉样式)下载</a></li><li><a href="http://www.digglife.cn/articles/wallpaper-windows7.html" title="9枚Windows 7高清壁纸">9枚Windows 7高清壁纸</a></li><li><a href="http://www.digglife.cn/articles/firefox-addons-weekly-issue3.html" title="一周Firefox扩展推荐-第三辑">一周Firefox扩展推荐-第三辑</a></li><li><a href="http://www.digglife.cn/articles/ubuntu-windows-xp-vista-firefox-profile.html" title="Ubuntu,Windows Vista和XP共享Firefox配置文件">Ubuntu,Windows Vista和XP共享Firefox配置文件</a></li><li><a href="http://www.digglife.cn/articles/add-compiz-fusion-stackswitch.html" title="Compiz Fusion新特效Stackswitch">Compiz Fusion新特效Stackswitch</a></li><li><a href="http://www.digglife.cn/articles/firefox3-themes-download-windows-mac.html" title="Windows XP,Vista和Mac版Firefox 3主题下载">Windows XP,Vista和Mac版Firefox 3主题下载</a></li><li><a href="http://www.digglife.cn/articles/cario-winows-shell-revolution.html" title="Cario:Windows桌面体验的革命,媲美Mac OS">Cario:Windows桌面体验的革命,媲美Mac OS</a></li></ul>";}'
bot_views:
  - 2337
views:
  - 3567
description:
  - 在Firefox下, 如果网页中出现中日混排的文字,而且网页设计者没有在CSS中做任何标明的话,日文通常会默认显示为宋体,这样会造成日文阅读十分艰难 (GReader下简直没有阅读的欲望).而在IE下,中日混排的文字一般情况下都会显示得比较完美,中文是宋体,日文是MS Gothic,不会出现日文被强制显示为宋体的情况.
syntaxhighlighter_encoded:
  - 1
duoshuo_thread_id:
  - 1154125469839262087
categories:
  - 火狐技巧
tags:
  - 中日混排
  - 字体
  - 日文字体
  - 火狐技巧
  - 美化

---
这是一个由来已久的问题.在<a title="火狐技巧" href="https://www.digglife.net/articles/category/firefox" target="_blank">Firefox</a>下,如果网页中出现中日混排的文字,而且网页设计者没有在CSS中做任何标明的话,日文通常会默认显示为宋体,非常丑陋,这样会造成日文阅读十分艰难(GReader下简直没有阅读的欲望).而在IE下,中日混排的文字一般情况下都会显示得比较完美,中文是宋体,日文是MS Gothic,不会出现日文被强制显示为宋体的情况.

<!--more-->

之前我的解决办法是将Firefox的默认字体更换成微软雅黑或者Meiryo,效果会稍微好一点,但是毕竟两者还是分别对应中文和日文,所以不能从根本上解决问题.

<span style="color: #ff6600;">中日混排文字在Firefox和IE下的显示效果对比,我们可以看到Firefox下的显示有多糟糕.</span>
  
[![中日混排在Firefox下的显示效果][1]][2]
  
[![中日混排在IE下的显示效果][3]][4]
  
解决思路很简单,就是寻找一个能够同时完美显示中日文的字体,<a title="华文细黑下载" href="http://www.rayfile.com/en/files/fb94ea3a-4f35-11dd-8ebd-001143e7b41c/" target="_blank">华文细黑</a>,<a title="丽黑Pro下载" href="http://www.rayfile.com/files/fb9674fd-4f35-11dd-a179-001143e7b41c/" target="_blank">丽黑</a>和<a title="文泉驿正黑下载" href="http://www.rayfile.com/files/fb97e973-4f35-11dd-8418-001143e7b41c/" target="_blank">文泉驿正黑</a>都能够实现这一点.我们可以将Firefox中文的默认字体更换为这两个.但是问题是这两个字体在<a title="Windows技巧" href="https://www.digglife.net/articles/category/windows-tricks" target="_blank">Windows</a>下的渲染效果很差,看着非常不舒服,所以我们还需要GDI++这个软件来优化渲染效果.

<a title="三种常见文字渲染方式比较" href="http://fisio.cn/compare-of-text-rendering.html" target="_blank">将整个系统的字体都更换为GDI++渲染的华文丽黑</a>当然也可以达到这个效果,而且整个Windows会非常漂亮.但是我在试用2天之后觉得有两点不好:GDI++会建立缓存,导致系统响应速度变慢,并且有些明显;整个系统都是华文丽黑看着很累.所以最终我还是选择了只对Firefox下的字体进行渲染.

步骤如下:

1.下载以上提到字体的任意一种并安装.下载<a title="gdi++下载" href="http://5rphea.bay.livefilestore.com/y1pDnB4SISnhhPHTDHJKW44jTl7M4p9D7koPqa3Gtffg23NlCM8jpt6ksnhfAcAI2EBnryZ0PtrPM4thd9wvtpC6SvkwpHQZvGS/gdi%2B%2B.zip" target="_blank">GDI++</a>.

2.右键点击Firefox快捷方式,将属性修改为如下模式:(其中gdi++所在路径根据自己的实际情况修改,注意双引号和空格)

目标:&#8221;D:\Program Files\gdi++\gdi++.exe&#8221; &#8220;D:\Program Files\firefox 3\firefox.exe&#8221;

起始位置:&#8221;D:\Program Files\gdi++&#8221;

[![][5]][6]

3.修改Firefox的默认字体为三种字体中的任意一个.在工具&#8211;选项&#8211;内容&#8211;字体和颜色中修改.

效果如下:
  
<span style="color: #ff0000;">丽黑Pro</span>
  
[![丽黑的显示效果][7]][8]
  
<span style="color: #ff0000;">华文细黑</span>
  
[![华文细黑的显示效果][9]][10]

<span style="color: #ff0000;">文泉驿正黑</span>

[![文泉驿正黑的显示效果][11]][12]

感觉上丽黑效果是最好的,不过因为太黑所以可能看久了会累,所以另外两个也值得一试.有关GDI++的详细信息和配置方法,大家还可以参考<a title="freetype版gdi++设置文件详解及问题解答" href="http://bbs.themex.net/showthread.php?t=16821991" target="_blank">极限主题的有关内容</a>.

<span style="color: #ff0000;">2009年1月2日更新字体下载链接.</span>

 [1]: http://digglife.qiniudn.com/wp-content/uploads/archive/jfont-ff.jpg
 [2]: http://picasaweb.google.com/digglifeshow/oCzYfC/photo#5221428927879359490
 [3]: http://digglife.qiniudn.com/wp-content/uploads/archive/jfont-ie.jpg
 [4]: http://picasaweb.google.com/digglifeshow/oCzYfC/photo#5221428929347822002
 [5]: http://digglife.qiniudn.com/wp-content/uploads/archive/firefox-gdi%2B%2B.png
 [6]: http://picasaweb.google.com/digglifeshow/oCzYfC/photo#5221714050451851490
 [7]: http://digglife.qiniudn.com/wp-content/uploads/archive/lihei.png
 [8]: http://picasaweb.google.com/digglifeshow/oCzYfC/photo#5221704418296133026
 [9]: http://digglife.qiniudn.com/wp-content/uploads/archive/wenquanyi.png
 [10]: http://picasaweb.google.com/digglifeshow/oCzYfC/photo#5221704419846810834
 [11]: http://digglife.qiniudn.com/wp-content/uploads/archive/zhenghei.png
 [12]: http://picasaweb.google.com/digglifeshow/oCzYfC/photo#5221704423913468114