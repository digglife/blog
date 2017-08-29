---
title: 关于Feed实际订阅量的分析
author: 摩摩诘
type: post
date: 2008-07-31T14:57:13+00:00
url: /articles/real-feed-subscribers.html
description:
  - 前些天看了月光博客写的一篇关于获取真实RSS订阅数的文章，因为我对DiggLife的2700个订阅者深表怀疑，所以当天我也在Feed中插入了雅虎统计代码，想知道有多少活人在阅读器里看DiggLife。
bot_views:
  - 1931
views:
  - 1077
syntaxhighlighter_encoded:
  - 1
duoshuo_thread_id:
  - 1154125469839262104
categories:
  - 博客研究
tags:
  - rss
  - rss阅读器
  - 博客营销
  - 鲜果

---
前些天看了月光博客写的一篇<a title="获取真实的RSS订阅数的方法" href="http://www.williamlong.info/archives/1427.html" target="_blank">关于获取真实RSS订阅数的文章</a>，因为我对DiggLife的2700个订阅者深表怀疑，所以当天我也在Feed中插入了雅虎统计代码，想知道有多少活人在阅读器里看DiggLife。

在插入统计代码之后我在28号和29号两天更新了两篇日志<a title="一键显示或隐藏文件" href="https://www.digglife.net/articles/hide-show-file-shortcut.html" target="_blank">一键显示或隐藏文件</a>，[网上在线观看北京奥运会直播的几种方法][1]，所以统计以这两天的为准。

从结果中我发现，月光说的”**在统计报告中的每天独立访问数UV就是准确的实际订阅量**“并不准确，因为[DiggLife][2]昨天（7月30日）的独立访问数超过了6000，我咋一看也吓了一跳，以为雅虎统计出了问题。那么这是为什么呢？下面看看统计报告中的分析。

<!--more-->

下面这个是DiggLife Feed在7月30日的统计：

<div style="width:410px" class="wp-caption aligncenter">
  <a href="http://picasaweb.google.com/digglifeshow/oCzYfC/photo#5229187779045824098"><img title="DiggLife的Feed访问数统计" src="http://digglife.qiniudn.com/wp-content/uploads/archive/feedview.png" alt="DiggLife的Feed访问数统计" width="400" height="258" /></a>
  
  <p class="wp-caption-text">
    DiggLife的Feed访问数统计，10时-15点时左右比较集中
  </p>
</div>

很明显，这绝对不是订阅器里能够产生的流量，因为到现在为止，DiggLife的订阅数的虚数都只在2700左右徘徊。

所以我马上查看了一下被访主机的数据，结果发现来自_xianguo.space.sina.com.cn_的访问占了总数的95%以上，从地址中的xianguo和sina，我马上联想到了海内集成的鲜果热文，所以估计这是鲜果和新浪合作的结果，可是输入上面这个地址无法访问，于是删掉前面的xianguo，真相大白，原来是<a title="新浪空间" href="http://space.sina.com" target="_blank">新浪空间</a>（从来没听说过）里面集成了鲜果阅读器（比和海内的合作要更加深入啊），而且默认的一个订阅为”每日鲜果精选“， 果然在这个个性化阅读器的首页看到了[网上在线观看北京奥运会直播的几种方法][1]这篇文章。

<div style="width:410px" class="wp-caption aligncenter">
  <a href="http://picasaweb.google.com/digglifeshow/oCzYfC/photo#5229187784071013986"><img title="DiggLife的Feed访问来源统计" src="http://digglife.qiniudn.com/wp-content/uploads/archive/feedsource.png" alt="真正直接来自阅读器的访问并不多" width="400" height="275" /></a>
  
  <p class="wp-caption-text">
    Feed访问量真正直接来自阅读器的并不多
  </p>
</div>

**所以雅虎的总体统计数据只是代表了Feed的访问量，如果要真正获得订阅数，还要除去这些直接通过热文等页面访问的人，那样我们需要除去的有鲜果热文，Feedsky的Feed主页，还有类似上面这样阅读器和其他网站合作的产物。**结果是，根据这两天的统计结果，DiggLife的活动订阅者只有500-600，比我预想的要低许多，果然应验了月光90%订阅数都是不准确的观点。

但是，我也觉得很欣慰，因为这又是一个博客的价值不能用传统指标来决定的明证，至少，应该加上Feed展示次数这个指标，如果按照Feedsky展示广告的价格，这一天展示广告仅仅来自鲜果的就应该有30多RMB，何况我认为这种价格还是远远低于实际产生的效应。

另外，鲜果的功能是RSS阅读器，但是其真正的价值是信息的聚合和推送。鲜果已经通过自己的开放为博客的展示创造了一个广阔的平台，而且这个平台还在不断扩张中，那么，作为内容产生者的博客能够真正从里面获得什么？页面流量?从我30日的Google分析统计上看，并没有多少是来自这里的，多数人在热文里面看过之后就算，很少进入原文查看。订阅?这不又转回来了么。

 [1]:https://www.digglife.net/articles/beijing-olympic-online.html "网上在线观看北京奥运会直播的几种方法"
 [2]:https://www.digglife.net/ "DiggLife"
