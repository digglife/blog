---
title: 让IE6崩溃只需一行代码
author: 摩摩诘
type: post
date: 2007-08-07T10:08:46+00:00
url: /articles/crash-your-ie-6-with-one-single-html-line.html
0:
  - b3a464a5b4a1dcfc45db064b11fbaf7a57c89019203823b7c7ef1750b414d42fe75bf97754917f44c79f8d3d39300a9c
  - b3a464a5b4a1dcfc45db064b11fbaf7a57c89019203823b7c7ef1750b414d42fe75bf97754917f44c79f8d3d39300a9c
1:
  - 819d6a8ba971667c1f7e6c3129322d83a06e9e920a0dc0894bd9c7757c9fc7cd3e49e7301786b9ce66fbee938a7972e8
  - 819d6a8ba971667c1f7e6c3129322d83a06e9e920a0dc0894bd9c7757c9fc7cd3e49e7301786b9ce66fbee938a7972e8
2:
  - e3d90fbdc9c1af1c1374b852c4cd867f51bd5d202a5f5db64ae9410e4cee54a159f8548f801c141ccc34f09803831d1b
  - e3d90fbdc9c1af1c1374b852c4cd867f51bd5d202a5f5db64ae9410e4cee54a159f8548f801c141ccc34f09803831d1b
comment_count:
  - 5
related_posts:
  - 'a:2:{s:4:"time";i:1224747252;s:13:"related_posts";s:1281:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/check-loading-time.html" title="比比看哪个网站加载更快">比比看哪个网站加载更快</a></li><li><a href="http://www.digglife.cn/articles/down-or-just-me.html" title="测试工具:网站到底挂了没?">测试工具:网站到底挂了没?</a></li><li><a href="http://www.digglife.cn/articles/join-google-experimental-search.html" title="现在就来参与测试Google实验搜索吧">现在就来参与测试Google实验搜索吧</a></li><li><a href="http://www.digglife.cn/articles/no-more-wga-for-ie7.html" title="IE 7新版发布,无需WGA正版验证">IE 7新版发布,无需WGA正版验证</a></li><li><a href="http://www.digglife.cn/articles/link-scrollover.html" title="技巧:给链接文字添加滚动变化效果">技巧:给链接文字添加滚动变化效果</a></li><li><a href="http://www.digglife.cn/articles/how-addicted-to-blogging-are-you.html" title="测试你的博客上瘾度">测试你的博客上瘾度</a></li><li><a href="http://www.digglife.cn/articles/%e4%bd%bf%e7%94%a8greasemonkey%e4%b8%aa%e6%80%a7%e5%8c%96%e4%bd%a0%e7%9a%84igoogle.html" title="使用Greasemonkey个性化你的iGoogle">使用Greasemonkey个性化你的iGoogle</a></li></ul>";}'
bot_views:
  - 1528
views:
  - 954
duoshuo_thread_id:
  - 1154125469839261878
categories:
  - 业界新闻
tags:
  - IE
  - 代码
  - 崩溃
  - 测试

---
一个名为<a href="http://d.hatena.ne.jp/Hamachiya2/20070804/browser_crasher" target="_blank">hamachiya2</a>的日本博客发现了仅仅一行HTML代码就能让IE 6崩溃,代码如下:

<pre>&lt;style&gt;*{position:relative}&lt;/style&gt;&lt;table&gt;&lt;input&gt;&lt;/table&gt;</pre>

如果你不信,可以点击<a href="http://immike.net/scripts/ie_crash.html" target="_blank">这个链接</a>尝试一下.这一段代码在Firefox,Opera和Safari中都能正常解析,但是在IE 6下会引起Mshtml.dll致命错误.

<a href="https://www.digglife.net/wp-content/uploads/3/379/2007/08/crash.png" atomicselection="true"><img src="https://www.digglife.net/wp-content/uploads/3/379/2007/08/crash-thumb.png" alt="Crash" height="135" width="450" /></a>

以上来自<a href="http://immike.net/blog/2007/08/06/single-line-of-html-crashes-ie-6/" target="_blank">immike</a>

其实在此之前已经有个名为<a href="http://www.crashie.com/" target="_blank">CrashIE</a>的网页发布了一段让IE 6-崩溃的代码,同样是只有一行,这一行代码是:

<font face="Courier New"><script>for(x in document.write){document.write(x);}</script></font>

CrashIE网站代码里就包含有这段代码,所以如果你使用IE 6内核的浏览器是无法看到页面的.它的目的是通过这个事实来推广另外3个浏览器.

但是,这些能成为IE不如其他浏览器的新证明么?
