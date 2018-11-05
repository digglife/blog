---
title: 使用Greasemonkey个性化你的iGoogle
author: 摩摩诘
type: post
date: 2007-05-17T09:46:21+00:00
url: /articles/使用greasemonkey个性化你的igoogle.html
0:
  - af9b738e1f7f7b8ceb56dd83f4a110ddbff00eaa3230c6427d5d70446d07754312dba05b201ee9fe9c55117eb6a34e00
  - af9b738e1f7f7b8ceb56dd83f4a110ddbff00eaa3230c6427d5d70446d07754312dba05b201ee9fe9c55117eb6a34e00
1:
  - wpAjax2492d6cd9c1a00568c2e7451fcb872dc671c286b890966a34eb800cca8ccff0ddd3003bfbd1be9fd93118487bc50737f
comment_count:
  - 3
related_posts:
  - 'a:2:{s:4:"time";i:1224752766;s:13:"related_posts";s:1291:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/popular-feeds-in-google-reader.html" title="Google Reader中文版里的推荐Feeds">Google Reader中文版里的推荐Feeds</a></li><li><a href="http://www.digglife.cn/articles/google-search-engine-for-ringtones.html" title="Google将发布手机铃声搜索">Google将发布手机铃声搜索</a></li><li><a href="http://www.digglife.cn/articles/how-to-download-published-google-docs.html" title="如何下载公开的Google文档和电子表格">如何下载公开的Google文档和电子表格</a></li><li><a href="http://www.digglife.cn/articles/programing-languages-map-in-google-maps.html" title="编程语言的Google地图:Hello World!世界">编程语言的Google地图:Hello World!世界</a></li><li><a href="http://www.digglife.cn/articles/geeky-google-calendars.html" title="奇客必备的8个特色Google日历">奇客必备的8个特色Google日历</a></li><li><a href="http://www.digglife.cn/articles/clean-your-igoogle.html" title="iGoogle:清理你的个性化主页">iGoogle:清理你的个性化主页</a></li><li><a href="http://www.digglife.cn/articles/google-logos.html" title="十个你可能从未见过的Google Logo">十个你可能从未见过的Google Logo</a></li></ul>";}'
bot_views:
  - 1557
views:
  - 1025
duoshuo_thread_id:
  - 1154125469839261765
categories:
  - 火狐技巧
tags:
  - google
  - iGoogle
  - javascipts
  - 个性化主页
  - 代码
  - 自定义

---
[<font color="#669966">iGoogle</font>][1],前身为Google Homepage的个性化主页服务.它有着极广的用户群,多样化的组件,以及简单友好的操作.但是,依然有一些细节不尽如人意,特别是界面被用户诟病已久,尽管加入主题选项,但是依然在很多方面有瑕疵.不过还好有Greasemonkey,我们可以最大化地自定义iGoogle.

使用以下技巧需要<a target="_blank" href="http://www.greasespot.net/"><font color="#669966">安装Greasemonkey</font></a>,一个通过简单的JavaScripts代码改变网页显示方式的Firefox插件(IE7目前通过IE7 Pro可以支持).你不需要会编写JavaScripts,因为网上有很多用户自发开发了很多实用代码,你需要做的只是点击几下鼠标而已.

**透明效果**

iGoogle的新主题很漂亮,但是有些网页元素(比如搜索框)把部分图片覆盖了,这严重损坏了页面的整体美观.这一段代码能够让类似元素透明,使主题能够显示得更完美.

[![igoogle.jpg][2]][3]

<a target="_blank" href="http://userstyles.org/style/show/2162"><font color="#669966">下载代码</font></a>

**去除&#8221;+&#8221;按钮**

如果你不喜欢每个项目那个该死的&#8221;+&#8221;,或者你从来不用它,可以使用这段代码将其完全去除.

<a target="_blank" href="http://userstyles.org/style/show/1766"><font color="#669966">下载代码</font></a>

**蓝色主题**

[![bluetheme.png][4]][5]
  
一个第三方蓝色主题.

<a target="_blank" href="http://googlesystem.blogspot.com/2007/01/google-personalized-homepage-blue.html"><font color="#669966">下载代码</font></a>

**自定义Logo**

不喜欢iGoogle的Logo.这段代码能够让你使用任何图片替换它.你需要找到或者制作一个166*55象素的图片,上传到任意空间得到链接,将这个图片链接加到#regular_logo中&#8221;background:url(&#8220;的后面.

<a target="_blank" href="http://userscripts.org/scripts/show/8953"><font color="#669966">下载代码</font></a>

[][6]

**移除多余空白**

使用这段代码能够去除组件之间的空白.注意,它可能和其他的代码冲突,特别是下面的Resizable Columns.

<a target="_blank" href="http://userstyles.org/style/show/1327"><font color="#669966">下载代码</font></a>

[][7]

**自定义组件大小**.

[![resizable.jpg][8]][9]

这段代码能让你充分利用每一寸空间,以放置更多项目.安装后直接左右拖拽项目边框改变大小.

<a target="_blank" href="http://userscripts.org/scripts/show/8162"><font color="#669966">下载代码</font></a>

[][10]

**单栏模式**

这个可能有点怪异,但是对一些用户同样有用.它能让整个iGoogle页面只显示一个项目.

<a target="_blank" href="http://userstyles.org/style/show/1509"><font color="#669966">下载代码</font></a>

**去除标题栏**

显示或隐藏组件的标题栏

<a target="_blank" href="http://userscripts.org/scripts/show/8201"><font color="#669966">下载代码</font></a>

**移除搜索栏**

如果你在iGoogle页面从不使用搜索,那就移除它吧.

<a target="_blank" href="http://userscripts.org/scripts/show/2496"><font color="#669966">下载代码</font></a>

**移除页脚**

看着页脚也不顺眼??移除&#8230;

<a target="_blank" href="http://userscripts.org/scripts/show/7736"><font color="#669966">下载代码</font></a>

**圆滑边角**

让组件边框更加圆滑.

<a target="_blank" href="http://userscripts.org/scripts/show/8772"><font color="#669966">下载代码</font></a>

**最大化可用空间**

[![maximize.png][11]][12]

Gooogle IG max代码,通过多种途径来挤出空间:移除标题栏,移除页脚,减小页面元素占用&#8230;

<a target="_blank" href="http://userscripts.org/scripts/show/7912"><font color="#669966">下载代码</font></a>

原文来自<a target="_blank" href="http://mashable.com/2007/05/11/igoogle/"><font color="#669966">Mashable</font></a>

 [1]: http://www.google.com/ig
 [2]: https://www.digglife.net/wp-content/uploads/3/379/2007/05/igoogle.jpg
 [3]: https://www.digglife.net/wp-content/uploads/3/379/2007/05/igoogle.jpg "igoogle.jpg"
 [4]: https://www.digglife.net/wp-content/uploads/3/379/2007/05/bluetheme.png
 [5]: https://www.digglife.net/wp-content/uploads/3/379/2007/05/bluetheme.png "bluetheme.png"
 [6]: http://userscripts.org/scripts/show/8953
 [7]: http://userstyles.org/style/show/1327
 [8]: https://www.digglife.net/wp-content/uploads/3/379/2007/05/resizable.jpg
 [9]: https://www.digglife.net/wp-content/uploads/3/379/2007/05/resizable.jpg "resizable.jpg"
 [10]: http://userscripts.org/scripts/show/8162
 [11]: https://www.digglife.net/wp-content/uploads/3/379/2007/05/maximize.png
 [12]: https://www.digglife.net/wp-content/uploads/3/379/2007/05/maximize.png "maximize.png"
