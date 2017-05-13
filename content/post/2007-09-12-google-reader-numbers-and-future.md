---
title: Google Reader背后的数字和未来走向
author: 摩摩诘
type: post
date: 2007-09-12T12:07:38+00:00
url: /articles/google-reader-numbers-and-future.html
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
  - d0f00eee74c76ae3d1ade1d7805847c08ad41ddfc44b5745b08f91503ac809f533972bafe1056da70e8615ba4215b7c4
  - d0f00eee74c76ae3d1ade1d7805847c08ad41ddfc44b5745b08f91503ac809f533972bafe1056da70e8615ba4215b7c4
1:
  - ea47b1cd1d4e2ead809673426d749cb83fd89b33ab1d7b21007fd6c00bcc02b229264d2096dd627e4f9e9f0503ed5522
  - ea47b1cd1d4e2ead809673426d749cb83fd89b33ab1d7b21007fd6c00bcc02b229264d2096dd627e4f9e9f0503ed5522
2:
  - e66fffdc465d13bf99f324b3478358c1d42c702976f08a9ce82e96694e1ba18f0b031e1744cb06a2203a878c934858c8
  - e66fffdc465d13bf99f324b3478358c1d42c702976f08a9ce82e96694e1ba18f0b031e1744cb06a2203a878c934858c8
3:
  - 8bd9401fdc00c7eda9f4e2cbc3391cacf246595610a9a313c47aa815ef6a4268446c54aa5927f685f3513b842d33cbb5
  - 8bd9401fdc00c7eda9f4e2cbc3391cacf246595610a9a313c47aa815ef6a4268446c54aa5927f685f3513b842d33cbb5
4:
  - 3f5c2daf42d10c38afc7f7bc4c45d49cf90dcc3e44108824cce16c082b052af11f59467b4397c20bcbe22af1d97a8261
  - 3f5c2daf42d10c38afc7f7bc4c45d49cf90dcc3e44108824cce16c082b052af11f59467b4397c20bcbe22af1d97a8261
5:
  - 2846d569d69bdd07b65a8d8fbf2140b348dac034b43fa9df981080b2a0badda24c0f16bafd97c8a381ed756fd5027205
  - 2846d569d69bdd07b65a8d8fbf2140b348dac034b43fa9df981080b2a0badda24c0f16bafd97c8a381ed756fd5027205
6:
  - 43fd27e3dfe7cdedf387e800f8a62ff0771af0b5f96796819c6acf104fa9c0bc04fc91e1e865ffd2ff5621c1ac0f9572
  - 43fd27e3dfe7cdedf387e800f8a62ff0771af0b5f96796819c6acf104fa9c0bc04fc91e1e865ffd2ff5621c1ac0f9572
comment_count:
  - 7
related_posts:
  - 'a:2:{s:4:"time";i:1224747395;s:13:"related_posts";s:1138:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/google-reader-top-recommendations.html" title="Google Reader首页新增个性化订阅推荐">Google Reader首页新增个性化订阅推荐</a></li><li><a href="http://www.digglife.cn/articles/popular-feeds-in-google-reader.html" title="Google Reader中文版里的推荐Feeds">Google Reader中文版里的推荐Feeds</a></li><li><a href="http://www.digglife.cn/articles/view-original-articles-inside-google-reader.html" title="在Google Reader内部查看Feed原文">在Google Reader内部查看Feed原文</a></li><li><a href="http://www.digglife.cn/articles/top-10-google-reader-tricks.html" title="十大Google Reader使用技巧">十大Google Reader使用技巧</a></li><li><a href="http://www.digglife.cn/articles/%e4%b8%aa%e6%80%a7%e5%8c%96google-reader%e7%9a%ae%e8%82%a4.html" title="个性化Google Reader皮肤">个性化Google Reader皮肤</a></li><li><a href="http://www.digglife.cn/articles/google-reader-tricks.html" title="Google Reader你可能不知道的一些技巧">Google Reader你可能不知道的一些技巧</a></li></ul>";}'
views:
  - 464
bot_views:
  - 1233
duoshuo_thread_id:
  - 1154125469839261927
categories:
  - 谷歌相关
tags:
  - google reader
  - 数据

---
Google Reader是我每天都要使用的RSS阅读服务,它同时也是<a title="订阅digglife" href="http://feed.digglife.cn" target="_blank">DiggLife订阅</a>数中占绝大多数的阅读器(48.9%,175个).根据数据统计,Google Reader也已经成为全球用户最多的RSS阅读器.那么Google到底花费了多大的空间来存储Feed,又是如何管理这些Feed的呢?下面我们来一探究竟:

<!--more-->

1.Google Reader区别对待两种Feed:

  * 只有一个读者的Feed(占Feed总量的2/3,每3个小时更新一次) 
  * 一个以上读者的Feed(每小时更新一次) 

2.Google Reader用了10 TB的容量来存储所有的原始数据

3.Google Reader每天要抓取800多万个Feed

4.Google Reader是主流在线RSS阅读器里惟一一个保留有所有Feed完整历史的阅读器.

5.许多Google应用程序都使用了Google Reader的核心架构来管理Feed:iGoogle,Gmail网络剪辑,Blogger Widgets,Google电子表格,Ajax API.用户所有涉及到Feed的操作都由Google Reader完成,它独立于Google博客搜索.

6.Google Reader用户的增长速度=Feed的增长速度(当然是Google Reader需要处理的Feed)

7.Google Reader的索引文件每周增长4%

8.Google Reader 70%的流量来自于<a title="火狐技巧" href="https://www.digglife.net/articles/category/firefox/" target="_blank">Firefox</a>

9.Gmai和Orkut是仅有的两个在流量上超过Google Reader的Google应用程序.

10.搜索功能需要庞大的计算资源.Google Reader为搜索功能使用了两种索引:

  * 一个每天更新2次的树形索引(150台机器,60亿个文档) 
  * 为即时文章准备的40个小型树形索引,每5分钟更新一次(40台机器,4亿个文档) 

11.未来会加入的功能:

  * 即将到来的:国际化,Feed推荐功能,接收发送到Google博客搜索的Ping 
  * 不久的将来:基于链接(链接到同一页面的文章)的简单聚合,给共享文章添加评论的功能. 
  * 盈利分享计划:在Feed中加入Google Adsense广告,和使用Adsense的博客主分享收入 

&#xA0;

来自<a title="Google Operating System" href="http://googlesystem.blogspot.com/2007/09/google-reader-numbers.html" target="_blank">Google OS</a>