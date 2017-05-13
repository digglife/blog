---
title: 如何下载公开的Google文档和电子表格
author: 摩摩诘
type: post
date: 2007-07-17T01:01:47+00:00
url: /articles/how-to-download-published-google-docs.html
related_posts:
  - 'a:2:{s:4:"time";i:1224882060;s:13:"related_posts";s:1360:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/customize-gmail-signature.html" title="Gmail技巧:让你的签名绚起来">Gmail技巧:让你的签名绚起来</a></li><li><a href="http://www.digglife.cn/articles/add-google-toolbar-functions-firefox3.html" title="给Firefox 3添加Google Toolbar的功能">给Firefox 3添加Google Toolbar的功能</a></li><li><a href="http://www.digglife.cn/articles/clean-up-desktop-improve-productivity-2.html" title="彻底清空桌面,让启动程序更加高效Part.2">彻底清空桌面,让启动程序更加高效Part.2</a></li><li><a href="http://www.digglife.cn/articles/clean-up-desktop-improve-productivity-1.html" title="彻底清空桌面,让启动程序更加高效Part.1">彻底清空桌面,让启动程序更加高效Part.1</a></li><li><a href="http://www.digglife.cn/articles/google-apps-firefox-sidebar.html" title="集装:在Firefox侧边栏载入Google应用">集装:在Firefox侧边栏载入Google应用</a></li><li><a href="http://www.digglife.cn/articles/google-android-sdk.html" title="[视频+截图]Google发布Android SDK">[视频+截图]Google发布Android SDK</a></li><li><a href="http://www.digglife.cn/articles/popular-feeds-in-google-reader.html" title="Google Reader中文版里的推荐Feeds">Google Reader中文版里的推荐Feeds</a></li></ul>";}'
bot_views:
  - 1828
views:
  - 5354
duoshuo_thread_id:
  - 1154125469839261847
categories:
  - 谷歌相关
tags:
  - google
  - 文档
  - 电子表格

---
<a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/07/dns.gif"><img align="right" width="35" src="http://digglife.qiniudn.com/wp-content/uploads/3/379/2007/07/dns-thumb.gif" alt="dns" height="35" /></a> 如果有人给你发送了一个只读[Google文档][1]或电子表格,你需要将其保存为PDF文件并从你的网站上链接到该PDF下载地址,该怎么做呢?这里有一个简单实用的方法.

**1.电子表格**

一个发布后的电子文档有一个类似如下的地址: <u>http://spreadsheets.google.com/pub?key=[ID]</u>. 为了得到该文件各种格式的下载地址,你需要在地址后加上**&output=**后缀.比如<u>http://spreadsheets.google.com/pub?key=[ID]&output=xls</u> ,你就得到了微软Excel格式的版本.其他有效的格式还有:pdf, ods (OpenOffice spreadsheets), csv, txt.

**2.电子文档**
  
发布后的文档的URL类似: <u>http://docs.google.com/View?docid=[ID]</u>. 你可以按照如下形式获得该文档各种格式版本的下载地址:<u>http://docs.google.com/MiscCommands?command=saveasdoc&exportformat=[FORMAT]&docID=[ID]</u>, [FORMAT]可以为以下任何一个值: pdf, doc, oo (OpenOffice documents), rtf, txt.

**注意:**

另外一个下载这些文件的方法是进入<a target="_blank" href="http://docs.google.com">Google文件的主页</a>打开,但是,至少对电子表格来说以上的方法可以让你直接链接到该文件各种格式版本的下载地址,而且让没有Google帐号的人也可以使用.对于电子文档,访问者还是需要在点击该文件之前登录他的Google帐号.理由不明.

来自[Google Operating System][2]

 [1]: https://www.digglife.net/articles/dictionary-in-google-docs.html
 [2]: http://googlesystem.blogspot.com/