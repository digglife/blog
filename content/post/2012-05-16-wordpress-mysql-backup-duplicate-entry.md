---
title: WordPress导入SQL备份出现Duplicate Entry的解决
author: 摩摩诘
type: post
date: 2012-05-15T17:48:27+00:00
url: /articles/wordpress-mysql-backup-duplicate-entry.html
index_image:
  - https://www.digglife.net/wp-content/uploads/2012/05/mysql.jpg
views:
  - 952
duoshuo_thread_id:
  - 1154125469839261838
categories:
  - 博客研究
tags:
  - mysql
  - wordpress

---
上周VPS当机，数据全部损毁，还好在另外一个服务器上还有一坨2011年的整站备份，2009年以来博客也基本处于荒废状态，数据损失并不大。加上Wordpress也装有备份插件，每周会发送sql备份到我的Gmail，所以日志完好无损。于是要灾后重建只需两步，恢复数据库，找回最近几篇日志的图片。

<!--more-->

首先恢复数据库。最简单的自然是通过PHPMyAdmin，本来以为点两下鼠标就可以洗洗睡的，结果出现以下极客符文。

<img title="duplicate-entry-primary-id" src="http://digglife.qiniudn.com/wp-content/uploads/2012/05/duplicate-entry-primary-id.png" alt="Duplicate Entry For Key Primary" width="500" height="135" />

MySQL表示`Duplicate Entry '3128' For Key 'Primary'`。我不懂MySQL同学在讲嘛也，于是加个Wordpress关键字去问Google，Google倒是有很多话说，可是都是没多大关联的blabla，有说数据结构不兼容的，有说插件臭虫的，线索太多无从下手。于是干脆自己分析，嘛，字面意思就是wp_post表里面的3128这个Primary Key重复了咯，那我删除重复的不就好了。

于是用<a title="TextWrangler" href="http://itunes.apple.com/cn/app/textwrangler/id404010395" target="_blank">TextWrangler</a>打开sql文档，搜索``INSERT INTO `wp_posts` VALUES (3128``，果然有两条重复记录，心想估计还有其他重复的，所以用Process Duplicate Lines功能查看所有重复项，果然有100多条重复记录，而且全部是日志图片相关，都是2010年5月之后的，不知道那个时候是发生了什么，个人猜测是Wordpress升级导致的，不过也不必深究了，关键在于速度解决问题。
  
<img title="all-duplicate-lines-sql-backup" src="http://digglife.qiniudn.com/wp-content/uploads/2012/05/all-duplicate-lines-sql-backup.png" alt="所有SQL备份中的重复记录" width="490" height="639" />
  
剩下的很明了，全选WP_Post表记录（因为整个sql文档中还有不少创建表的语句重复，避免误杀），利用重复行删除功能uniq一下。保存打包，重新上传，果然顺利插入，高潮迭起。

然后是找回图片。本来弱弱地想Google Cache/RSS Feed之类的可能会缓存到图片，结果证明果然我比钟欣桐还天真，图片一概空白。万般无奈只好用标题Google，指望从转载中找回。倒是有不少结果，PCHome驱动之家等无断拷贝成瘾的网站都给图片加上了恶心的水印，好在还有搜狐科技、CnBeta之类有良的，有的干脆连文件名都不改，省了我不少功夫，鼻涕都感动出来了，我还真没想到有一天要靠这些个全文转载不留链接的同志们救命。有些首页索引缩略图找不到的，自己在找回图片的基础上稍加编辑了一下也OK了。

前前后后花了几个小时，终于大功告成。其实还有一些断断续续修改的网页代码没法恢复，一时也记不起来了，由他去吧。

中文博客的黄金时代（个人以为是2005-2008）过去之后，我就很少写博客，原因很多，其中最主要的一个是，在技术方面学到的越多，就觉得自己越无知，于是越耻于分享。现在看以前的好多日志都脸红不已。但是毕竟在这个地方，我曾经花费了很多心血，也收获了很多物质和精神上的鼓励，所以希望他一直存在，而且，要完好无损。