---
title: Greasemonkey:给Google Reader添加搜索框
author: 摩摩诘
type: post
date: 2007-07-20T06:12:09+00:00
url: /articles/greasemonkey-add-search-box-to-google-reader.html
0:
  - 3ed0b76356554e04b86fa7fb8d4e9cac322d333458a3b43b6f941c68cff809724679ff0ee0cfedba164afc68d838fade
  - 3ed0b76356554e04b86fa7fb8d4e9cac322d333458a3b43b6f941c68cff809724679ff0ee0cfedba164afc68d838fade
1:
  - 19293fda4744835f48df78345a486931d4911f5bd017f45ceebfba5972ac950a6b530ca0db27aec4585ef576352b8c8f
  - 19293fda4744835f48df78345a486931d4911f5bd017f45ceebfba5972ac950a6b530ca0db27aec4585ef576352b8c8f
2:
  - a33d4ed9d5d98dff882042912504a4131e414ac9c5211a97f0c11f1f08f09e065addb626b27908be6c37612c178a0c02
  - a33d4ed9d5d98dff882042912504a4131e414ac9c5211a97f0c11f1f08f09e065addb626b27908be6c37612c178a0c02
3:
  - 41449977e4e7e562bd2987c19aaba9ba71e50e13a4a7427026a404a9ec92244bc0aefc444101e8e2067cab4502b13f3a
  - 41449977e4e7e562bd2987c19aaba9ba71e50e13a4a7427026a404a9ec92244bc0aefc444101e8e2067cab4502b13f3a
4:
  - 376252346064fadb91a1406f9e9fd9974fba9c30612028e717e18f8a04f40d5bccb0f5668eb7ba3f47f00f3b81c544b6
  - 376252346064fadb91a1406f9e9fd9974fba9c30612028e717e18f8a04f40d5bccb0f5668eb7ba3f47f00f3b81c544b6
5:
  - 9c0e9391ede1fe11b4023b8306057993bd946e10b3216359efa52fa5790109f5cc585e97de492821b31d8bbeffe679f5
  - 9c0e9391ede1fe11b4023b8306057993bd946e10b3216359efa52fa5790109f5cc585e97de492821b31d8bbeffe679f5
comment_count:
  - 5
related_posts:
  - 'a:2:{s:4:"time";i:1224747266;s:13:"related_posts";s:1362:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/google-apps-firefox-sidebar.html" title="集装:在Firefox侧边栏载入Google应用">集装:在Firefox侧边栏载入Google应用</a></li><li><a href="http://www.digglife.cn/articles/manage-multiple-accouts-without-logging-off.html" title="同时管理同一网站的不同帐户:CookieSwap">同时管理同一网站的不同帐户:CookieSwap</a></li><li><a href="http://www.digglife.cn/articles/17-firefox-extensions-that-make-blogging-easy.html" title="Firefox:17个Firefox扩展让你&#34;博&#34;得更爽.">Firefox:17个Firefox扩展让你&#34;博&#34;得更爽.</a></li><li><a href="http://www.digglife.cn/articles/firefox_speed_dail.html" title="Firefox扩展:使用Speed Dial预览多个网页">Firefox扩展:使用Speed Dial预览多个网页</a></li><li><a href="http://www.digglife.cn/articles/firefox-addons-weekly-issue3.html" title="一周Firefox扩展推荐-第三辑">一周Firefox扩展推荐-第三辑</a></li><li><a href="http://www.digglife.cn/articles/firefox-addons-weekly-issue2.html" title="一周Firefox扩展推荐-第二辑">一周Firefox扩展推荐-第二辑</a></li><li><a href="http://www.digglife.cn/articles/firefox-addons-weekly-issue1.html" title="一周Firefox扩展推荐-第一辑">一周Firefox扩展推荐-第一辑</a></li></ul>";}'
views:
  - 536
bot_views:
  - 1314
duoshuo_thread_id:
  - 1154125469839261852
categories:
  - 火狐技巧
tags:
  - 扩展

---
Google Reader作为搜索起家的Google旗下产品不支持搜索功能,<a href="http://wpcache.yo2.cn/wp-content/uploads/3/379/2007/07/googlereader-logo.png" atomicselection="true"><img height="66" alt="googlereader_logo" src="https://www.digglife.net/qiniu/1276/image/6757dbeaa3d90336c2bacd4ebf093813.png" width="156" align="right" /></a>这不得不说是一个巨大的遗憾,而且比较匪夷所思.无论<a href="https://www.digglife.net/articles/%e5%8d%81%e5%a4%a7google-reader%e4%bd%bf%e7%94%a8%e6%8a%80%e5%b7%a7.html" target="_blank">我们能够多么方便地使用Google Reader</a>,但是需要搜索有点印象的相关文章内容时,Google却毫无办法.当然,为了实现这一搜索功能,我们可以[使用Google自定义搜索引擎][1],或者甚至使用<a href="https://www.digglife.net/articles/google-gears-released.html" target="_blank">Google Gears</a>(<a href="http://www.gseeker.com/50226711/cgoogle_readeraeceiefirefoxeie_99773.php" target="_blank">How-to</a>&nbsp; 来自GSeek).尽管步骤也不算太复杂,但是已经远离的集成搜索的概念.

现在又这么一个<a href="http://greasespot.net/" target="_blank">Greasemonkey</a>代码能够直接在Google Reader加入搜索框,让搜索更加方便.它同时提供了文章范围搜索功能,你可以设定需要搜索的文章的新旧程度和数量.

<a href="http://wpcache.yo2.cn/wp-content/uploads/3/379/2007/07/grsearch.png" atomicselection="true"><img height="45" alt="GRsearch" src="https://www.digglife.net/qiniu/1276/image/435f87dcb574213be1a615f5027e4b27.png" width="450" /></a>

下载:<a href="http://userscripts.org/scripts/show/7062" target="_blank">Google Reader Search</a> (点击直接安装)

来自<a href="http://www.lifehacker.com" target="_blank">Lifehacker</a>

附: <a title="custom" name="custom"></a><a title="custom" name="custom"></a>**如何使用Google自定义搜索引擎搜索Google Reader.**

1.进入你的google reader后,定位到设置&#8211;导入导出,导出OPML文件保存到本地.

2.在Google Co-op里创建一个搜索引擎.任意输入一个名字,描述,关键字,然后在list of sites to search里面任意输入一些假网站(比如:www.example.com.当然,你可以输入一些你的确想搜索到的网站,比如加上DiggLife.),然后选择&#8221;search only these sites&#8221;,最后点击Next和Finish.这一步是为了让你的搜索引擎不会搜索到除Google Reader里面的页面之外的结果.

3.现在在你刚刚创建的搜索引擎旁单击control panel.选择&#8221;Advanced&#8221;,在annotations 一栏将你刚才保存的文件上传.这样,你的个性化Google Reader搜索引擎就打造完毕了.

话说上面的文字本来是<a href="http://www.cnbeta.com/articles/19896.htm" target="_blank">我N久之前投递到Cnbeta上的</a>(年代久远,因此略有改动),今天为了Google相关文章的时候跑到了17tech,看着看着觉得怎么这么眼熟啊,于是到Cnbeta上搜索相关关键字,发现果然有摩摩诘投递的字样.17tech连Cnbeta的链接都没有加上,两个真是冤家啊~~~~

 [1]: #custom
