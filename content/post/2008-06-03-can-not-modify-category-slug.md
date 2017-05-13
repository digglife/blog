---
title: WordPress无法编辑分类缩略名(Slug)的解决
author: 摩摩诘
type: post
date: 2008-06-03T12:34:34+00:00
url: /articles/can-not-modify-category-slug.html
comment_count:
  - 15
related_posts:
  - 'a:2:{s:4:"time";i:1224797369;s:13:"related_posts";s:1421:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/seo-tips-for-wordpress-bloggers.html" title="所有博客都应该了解的16条SEO技巧">所有博客都应该了解的16条SEO技巧</a></li><li><a href="http://www.digglife.cn/articles/11-things-before-you-publish.html" title="博客技巧:发布文章前必做的11件事.">博客技巧:发布文章前必做的11件事.</a></li><li><a href="http://www.digglife.cn/articles/17-firefox-extensions-that-make-blogging-easy.html" title="Firefox:17个Firefox扩展让你&#34;博&#34;得更爽.">Firefox:17个Firefox扩展让你&#34;博&#34;得更爽.</a></li><li><a href="http://www.digglife.cn/articles/20%e6%ac%be%e7%bb%9d%e5%af%b9%e4%b8%8d%e4%bc%9a%e8%ae%a9%e4%bd%a0%e5%a4%b1%e6%9c%9b%e7%9a%84wordpress%e6%a8%a1%e7%89%88.html" title="20款绝对不会让你失望的Wordpress模版.">20款绝对不会让你失望的Wordpress模版.</a></li><li><a href="http://www.digglife.cn/articles/8%e6%ac%be%e4%bc%98%e9%9b%85%e7%ae%80%e6%b4%81%e7%9a%84wordpress%e6%a8%a1%e7%89%88.html" title="8款优雅简洁的Wordpress模版">8款优雅简洁的Wordpress模版</a></li><li><a href="http://www.digglife.cn/articles/first-look-wordpress.html" title="传说中的wordpress&#8230;">传说中的wordpress&#8230;</a></li><li><a href="http://www.digglife.cn/articles/say-hello.html" title="回来打个招呼">回来打个招呼</a></li></ul>";}'
views:
  - 1146
bot_views:
  - 1782
duoshuo_thread_id:
  - 1154125469839262072
categories:
  - 博客研究
tags:
  - wordpress
  - 博客

---
今天在获得<a title="Google网站管理员工具改版,新增订阅统计" href="https://www.digglife.net/articles/google-webmaster-tools-redesign.html" target="_blank">Google管理员工具</a>的抓取错误信息之后想整理一下分类和标签,发现当修改<a title="分类缩略名具体说明" href="http://codex.wordpress.org/Glossary#Slug" target="_blank">分类缩略名</a>(Slug)的时候Wordpress始终提示"分类未更新",亦然保持原有的缩略名.用Google搜索了一圈之后没有找到相关文章,只好用英文搜索相关内容,最终发现了原因所在和<a title="Can’t edit category slug ?" href="http://imknight.net/archives/2008/01/20/cant-edit-category-slug/" target="_blank">解决方案</a>.

造成无法更改分类缩略名的原因很简单,<a title="Wordpress" href="https://www.digglife.net/articles/tag/wordpress" target="_blank">WordPress</a> 2.3及以上的版本由于引进了标签功能,Wordpress数据库结构发生了变化,链接分类,日志分类和标签被整合到wp_terms表中(<a title="Wordpress数据库说明文档2.3" href="http://codex.wordpress.org/Database_Description/2.3" target="_blank">这个页面</a>有详细说明).由于分类缩略名必须唯一,所以如果你已经使用了某个词作为标签或者链接分类,那么你将无法将其作为分类缩略名.

<!--more-->


  
<!--more-->

知道原因之后解决起来就非常简单了,无非是使用另外一个分类缩略名或者删除那个重复的标签.这就要看哪个损失比较小了,如果你的日志里已经多次连接到这个分类,那么最好使用<a title="Simple Tags" href="http://wordpress.org/extend/plugins/simple-tags/" target="_blank">Simple Tags</a>删除或者修改标签,反之则修改分类缩略名.

所以说,如果你的<a title="博客" href="https://www.digglife.net/articles/tag/%e5%8d%9a%e5%ae%a2" target="_blank">博客</a>才建立不久,最好确定所有应该固定下来的链接,比如页面缩略名,分类缩略名,日志永久链接结构等,不然修改起来会非常麻烦,而且会造成不必要的损失.</p> </p> </p> 

顺便求助一下:Google网站管理员工具提示了接近100个无法找到的网址,我发现很多是添加链接的时候失误,或者链接后来变化造成,但是单单根据Google网站管理员提供的一个链接很难定位到问题所在的网址,不知道大家有没有什么快速简便的办法解决这些死链?谢谢了!