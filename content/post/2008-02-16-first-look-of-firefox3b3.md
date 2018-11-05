---
title: Firefox 3 Beta 3新特性体验
author: 摩摩诘
type: post
date: 2008-02-16T10:03:44+00:00
url: /articles/first-look-of-firefox3b3.html
keywords:
  - firefox, 下载, 体验, 软件
description:
  - Firefox 3 Beta 3本周一就发布了, 这个Beta版和Beta 2相比改进的地方很多,基本上已经具备正式版本的大部分新特性.在Firefox 3的第一个RC发布之前,只会有一个Beta 4了,留给Firefox团队的时间无多.在使用了差不多一天时间之后我能够明显感觉到性能和易用性上的提升,让我对Firefox 3正式版更加期待了.
comment_count:
  - 7
related_posts:
  - 'a:2:{s:4:"time";i:1224888314;s:13:"related_posts";s:1278:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/firefox3rc1-download-improvements.html" title="Firefox 3 RC1发布,绿色便携版下载">Firefox 3 RC1发布,绿色便携版下载</a></li><li><a href="http://www.digglife.cn/articles/firefox3-beta5.html" title="Firefox 3 Beta 5发布,绿色便携版下载">Firefox 3 Beta 5发布,绿色便携版下载</a></li><li><a href="http://www.digglife.cn/articles/ie8-new-features-download.html" title="IE 8 Beta 1简体中文版下载和新功能介绍">IE 8 Beta 1简体中文版下载和新功能介绍</a></li><li><a href="http://www.digglife.cn/articles/custom-windows-interface-tools.html" title="9个工具打造焕然一新的Windows界面">9个工具打造焕然一新的Windows界面</a></li><li><a href="http://www.digglife.cn/articles/convert-powerpoint-flash.html" title="免费将Powerpoint转换为Flash">免费将Powerpoint转换为Flash</a></li><li><a href="http://www.digglife.cn/articles/firefox3-themes-download-windows-mac.html" title="Windows XP,Vista和Mac版Firefox 3主题下载">Windows XP,Vista和Mac版Firefox 3主题下载</a></li><li><a href="http://www.digglife.cn/articles/firefox3-download-day.html" title="Go Go Go!Firefox 3!">Go Go Go!Firefox 3!</a></li></ul>";}'
bot_views:
  - 2587
views:
  - 858
duoshuo_thread_id:
  - 1154125469839262026
categories:
  - 火狐技巧
tags:
  - firefox 3
  - 体验
  - 软件

---
<a href="http://www.mozilla.com/en-US/firefox/all-beta.html" target="_blank">Firefox 3 Beta 3</a>本周一就<a href="http://www.mozilla.com/en-US/firefox/3.0b3/releasenotes/" target="_blank">发布</a>了,这个Beta版和Beta 2相比改进的地方很多,基本上已经具备正式版本的大部分新特性.在Firefox 3的第一个RC发布之前,只会有一个Beta 4了,留给Firefox团队的时间无多.在使用了差不多一天时间之后我能够明显感觉到性能和易用性上的提升,让我对Firefox 3正式版更加期待了.

Firefox 3 Beta 3的改进体现在许多方面,比较显著的包括各个操作系统平台的全新原生界面,集成扩展搜索和安装,增强的Place和应用程序管理,网站身份验证等等.

<!--more-->

为了能够顺畅地使用Firefox 3 Beta 3,并且让它不和电脑中已经安装的Firefox 2产生交叉感染的状况,最好下载Firefox 3 Beta 3的英文便携版,然后将中文的语言文件(说实话,这个官方的翻译不怎么样)复制到相应的安装目录.本来网上已经有中文化的便携版,不过对原版做出了修改.

**1.**<a href="http://portableapps.com/apps/internet/firefox_portable/test" title="Firefox 3 Beta 3英文便携版下载" target="_blank"><strong>Firefox 3 Beta 3英文便携版下载</strong></a>**|**<a href="http://www.91files.com/?0G3K9A632MBIDAJDUPLN" title="Firefox 3 beta 3中文语言文件下载" target="_blank"><strong>中文语言文件下载</strong></a>**.**

直接将语言文件压缩包中的两个文件复制到\App\firefox\chrome里面,重启浏览器即可.

**2.**<a href="http://www.91files.com/?0FJL7P1K561DQ2DT0F2L" title="Firefox 3 Beta 3最新插件包下载" target="_blank"><strong>Firefox 3 Beta 3最新插件包下载</strong></a>**.**

解压后将所有文件复制到\App\firefox\plugins里面,重启浏览器.

**3.扩展无法使用的解决.**

其实已经有一些流行扩展在第一时间做出了更新,比如Greasemonkey,stylish,Better Gmail,Google Notebook等等.但是大部分扩展还是不兼容,这时我们可以禁用扩展的更新安全检查和兼容性检查.具体步骤如下:

  * 在地址栏输入about:config,点击&#8221;我保证会小心&#8221;.
  * 在界面任意地方右击,选择新建-布尔,在弹出窗口中输入`extensions.checkCompatibility`,并将其设置为false.同上新建一个`extensions.checkUpdateSecurity`的布尔类型,将其值设置为false.
  * 重启firefox.

这样大部分扩展都可以正常使用,尽管扩展管理器里不兼容的扩展依然有红色感叹号.当然,也有很多扩展还是不能使用,比如Google Toolbar.

完成以上工作之后,使用Firefox 3 Beta 3浏览网页就会很舒服了.

**Windows XP下的原生界面.**

主页按钮默认被移到了书签工具栏,不过通过定制功能把它恢复到导航工具栏.

[<img src="https://www.digglife.net/wp-content/uploads/3/379/2008/02/firefox3-ui-thumb.png" style="border-width: 0px" alt="firefox3-UI" border="0" height="384" width="449" />][1]

图标也都焕然一新(那个狐很有意思.Firefox在推广汉字&#8230;)

[<img src="https://www.digglife.net/wp-content/uploads/3/379/2008/02/firefox3-icons-thumb.png" style="border-width: 0px" alt="firefox3-icons" border="0" height="50" width="410" />][2]

**扩展管理更加方便**.现在可以直接在Firefox里搜索,下载和安装扩展,非常方便,想必也是Mozilla出于推广Firefox扩展的考虑.

[<img src="https://www.digglife.net/wp-content/uploads/3/379/2008/02/firefox3-addons-manager-thumb.png" style="border-width: 0px" alt="firefox3-addons-manager" border="0" height="419" width="450" />][3]

**完善的Place功能**

Firefox 3中新增的Place是最引人瞩目的改进.使用Place你可以搜索浏览历史,收藏和标签,你可以选择搜索的范围,搜索的规则,并可以将搜索保存至Smart Bookmark.Beta 3还新增了**备份和恢复功能**.

[<img src="https://www.digglife.net/wp-content/uploads/3/379/2008/02/firefox3-place-thumb.png" style="border-width: 0px" alt="firefox3-place" border="0" height="375" width="450" />][4]

与此相关,地址栏的星号收藏按钮在操作上也做了改变,单击直接收藏,双击归类和打标签.

[<img src="https://www.digglife.net/wp-content/uploads/3/379/2008/02/firefox3-bookmark-thumb.png" style="border-width: 0px" alt="firefox3-bookmark" border="0" height="185" width="323" />][5]

除了能够看见的这些改进之外,我能明显感觉到网页打开速度和响应速度的提升,应该不是心里暗示造成的.希望Firefox团队能够在3月份不负众望,推出令人满意的正式版.

 [1]: https://www.digglife.net/wp-content/uploads/3/379/2008/02/firefox3-ui.png
 [2]: https://www.digglife.net/wp-content/uploads/3/379/2008/02/firefox3-icons.png
 [3]: https://www.digglife.net/wp-content/uploads/3/379/2008/02/firefox3-addons-manager.png
 [4]: https://www.digglife.net/wp-content/uploads/3/379/2008/02/firefox3-place.png
 [5]: https://www.digglife.net/wp-content/uploads/3/379/2008/02/firefox3-bookmark.png
