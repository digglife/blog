---
title: 关于Wordpress2.6的图片说明(image Captioin)
author: 摩摩诘
type: post
date: 2008-07-16T05:00:32+00:00
url: /articles/about-wordpress26-image-caption.html
description:
  - Wordpress2.6昨天正式发布,DiggLife也在第一时间升级到了2.6版.这个版本新增了一个个人觉得很不错的小功能\"图片说明\"(Image Caption),能够在图片周围加上方便读者理解的说明文字.
comment_count:
  - 7
related_posts:
  - 'a:2:{s:4:"time";i:1224884243;s:13:"related_posts";s:1408:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/can-not-modify-category-slug.html" title="Wordpress无法编辑分类缩略名(Slug)的解决">Wordpress无法编辑分类缩略名(Slug)的解决</a></li><li><a href="http://www.digglife.cn/articles/digglife-new-theme-online.html" title="DiggLife新主题Beta中&#8230;">DiggLife新主题Beta中&#8230;</a></li><li><a href="http://www.digglife.cn/articles/different-sidebar-in-different-pages.html" title="如何让Wordpress模板在不同页面显示不同侧边栏">如何让Wordpress模板在不同页面显示不同侧边栏</a></li><li><a href="http://www.digglife.cn/articles/sidebar-widgets-support.html" title="如何让Wordpress模板支持Sidebar Widgets(侧边栏插件)">如何让Wordpress模板支持Sidebar Widgets(侧边栏插件)</a></li><li><a href="http://www.digglife.cn/articles/wordpress-comment-notifier.html" title="桌面版Wordpress评论提醒工具">桌面版Wordpress评论提醒工具</a></li><li><a href="http://www.digglife.cn/articles/3-column-wordpress-themes.html" title="20款美观的三栏Wordpress主题模板">20款美观的三栏Wordpress主题模板</a></li><li><a href="http://www.digglife.cn/articles/24-fresh-usable-and-elegant-wordpress-themes.html" title="24款新鲜,易用,优雅的Wordpress主题模板">24款新鲜,易用,优雅的Wordpress主题模板</a></li></ul>";}'
views:
  - 1134
bot_views:
  - 1596
duoshuo_thread_id:
  - 1154125469839261837
wp-syntax-cache-content:
  - |
    a:1:{i:1;s:5233:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="line_numbers"><pre>1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    17
    18
    19
    20
    21
    22
    23
    24
    25
    26
    27
    28
    29
    30
    31
    32
    33
    34
    </pre></td><td class="code"><pre class="css" style="font-family:monospace;">&nbsp;
    <span style="color: #808080; font-style: italic;">/* Captions */</span>
    .aligncenter<span style="color: #00AA00;">,</span>
    div<span style="color: #6666ff;">.aligncenter</span> <span style="color: #00AA00;">&#123;</span>
    <span style="color: #000000; font-weight: bold;">display</span><span style="color: #00AA00;">:</span> <span style="color: #993333;">block</span><span style="color: #00AA00;">;</span>
    <span style="color: #000000; font-weight: bold;">margin-left</span><span style="color: #00AA00;">:</span> <span style="color: #993333;">auto</span><span style="color: #00AA00;">;</span>
    <span style="color: #000000; font-weight: bold;">margin-right</span><span style="color: #00AA00;">:</span> <span style="color: #993333;">auto</span><span style="color: #00AA00;">;</span>
    <span style="color: #00AA00;">&#125;</span>
    &nbsp;
    <span style="color: #6666ff;">.wp-caption</span> <span style="color: #00AA00;">&#123;</span>
    <span style="color: #000000; font-weight: bold;">border</span><span style="color: #00AA00;">:</span> <span style="color: #933;">1px</span> <span style="color: #993333;">solid</span> <span style="color: #cc00cc;">#ddd</span><span style="color: #00AA00;">;</span>
    <span style="color: #000000; font-weight: bold;">text-align</span><span style="color: #00AA00;">:</span> <span style="color: #993333;">center</span><span style="color: #00AA00;">;</span>
    <span style="color: #000000; font-weight: bold;">background-color</span><span style="color: #00AA00;">:</span> <span style="color: #cc00cc;">#f3f3f3</span><span style="color: #00AA00;">;</span>
    <span style="color: #000000; font-weight: bold;">padding-top</span><span style="color: #00AA00;">:</span> <span style="color: #933;">4px</span><span style="color: #00AA00;">;</span>
    <span style="color: #000000; font-weight: bold;">margin</span><span style="color: #00AA00;">:</span> <span style="color: #933;">10px</span><span style="color: #00AA00;">;</span>
    -moz-border-radius<span style="color: #00AA00;">:</span> <span style="color: #933;">3px</span><span style="color: #00AA00;">;</span>
    -khtml-border-radius<span style="color: #00AA00;">:</span> <span style="color: #933;">3px</span><span style="color: #00AA00;">;</span>
    -webkit-border-radius<span style="color: #00AA00;">:</span> <span style="color: #933;">3px</span><span style="color: #00AA00;">;</span>
    <span style="color: #000000; font-weight: bold;">border-radius</span><span style="color: #00AA00;">:</span> <span style="color: #933;">3px</span><span style="color: #00AA00;">;</span>
    <span style="color: #00AA00;">&#125;</span>
    &nbsp;
    <span style="color: #6666ff;">.wp-caption</span> img <span style="color: #00AA00;">&#123;</span>
    <span style="color: #000000; font-weight: bold;">margin</span><span style="color: #00AA00;">:</span> <span style="color: #cc66cc;">0</span><span style="color: #00AA00;">;</span>
    <span style="color: #000000; font-weight: bold;">padding</span><span style="color: #00AA00;">:</span> <span style="color: #cc66cc;">0</span><span style="color: #00AA00;">;</span>
    <span style="color: #000000; font-weight: bold;">border</span><span style="color: #00AA00;">:</span> <span style="color: #cc66cc;">0</span> <span style="color: #993333;">none</span><span style="color: #00AA00;">;</span>
    <span style="color: #00AA00;">&#125;</span>
    &nbsp;
    <span style="color: #6666ff;">.wp-caption</span> p<span style="color: #6666ff;">.wp-caption-text</span> <span style="color: #00AA00;">&#123;</span>
    <span style="color: #000000; font-weight: bold;">font-size</span><span style="color: #00AA00;">:</span> <span style="color: #933;">11px</span><span style="color: #00AA00;">;</span>
    <span style="color: #000000; font-weight: bold;">line-height</span><span style="color: #00AA00;">:</span> <span style="color: #933;">17px</span><span style="color: #00AA00;">;</span>
    <span style="color: #000000; font-weight: bold;">padding</span><span style="color: #00AA00;">:</span> <span style="color: #cc66cc;">0</span> <span style="color: #933;">4px</span> <span style="color: #933;">5px</span><span style="color: #00AA00;">;</span>
    <span style="color: #000000; font-weight: bold;">margin</span><span style="color: #00AA00;">:</span> <span style="color: #cc66cc;">0</span><span style="color: #00AA00;">;</span>
    <span style="color: #00AA00;">&#125;</span>
    <span style="color: #808080; font-style: italic;">/* End captions */</span></pre></td></tr></table><p class="theCode" style="display:none;">
    /* Captions */
    .aligncenter,
    div.aligncenter {
    display: block;
    margin-left: auto;
    margin-right: auto;
    }
    
    .wp-caption {
    border: 1px solid #ddd;
    text-align: center;
    background-color: #f3f3f3;
    padding-top: 4px;
    margin: 10px;
    -moz-border-radius: 3px;
    -khtml-border-radius: 3px;
    -webkit-border-radius: 3px;
    border-radius: 3px;
    }
    
    .wp-caption img {
    margin: 0;
    padding: 0;
    border: 0 none;
    }
    
    .wp-caption p.wp-caption-text {
    font-size: 11px;
    line-height: 17px;
    padding: 0 4px 5px;
    margin: 0;
    }
    /* End captions */</p></div>
    ";}
categories:
  - 博客研究
tags:
  - wordpress
  - 图片说明
  - 新功能

---
WordPress2.6昨天<a title="Wordpress2.6的发布报告" href="http://wordpress.org/development/2008/07/wordpress-26-tyner/" target="_blank">正式发布</a>,DiggLife也在第一时间升级到了2.6版.这个版本新增了一个个人觉得很不错的小功能&#8221;图片说明&#8221;(Image Caption),能够在图片周围加上方便读者理解的说明文字.Wordpress2.6这个功能的真正意义是新增了一个Captioin的标签,而且在后台编辑图片的时候有一个Caption文本框,至于在日志中如何显示,要视乎主题CSS文件中对Caption的定义.

<!--more-->

<div style="width: 476px" class="wp-caption aligncenter">
  <img title="Wordpress2.6" src="http://digglife.qiniudn.com/qiniu/2589/image/f609b3ef50b95f84086204e52ee2407e.png" alt="图片说明就是类似这样的效果" width="466" height="303" />
  
  <p class="wp-caption-text">
    图片说明就是类似这样的效果
  </p>
</div>

如果你足够细心的话,可以看到Wordpress2.6默认主题的CSS代码相比以前的版本新增了如下一段:

<pre lang="css" line="1">/* Captions */
.aligncenter,
div.aligncenter {
display: block;
margin-left: auto;
margin-right: auto;
}

.wp-caption {
border: 1px solid #ddd;
text-align: center;
background-color: #f3f3f3;
padding-top: 4px;
margin: 10px;
-moz-border-radius: 3px;
-khtml-border-radius: 3px;
-webkit-border-radius: 3px;
border-radius: 3px;
}

.wp-caption img {
margin: 0;
padding: 0;
border: 0 none;
}

.wp-caption p.wp-caption-text {
font-size: 11px;
line-height: 17px;
padding: 0 4px 5px;
margin: 0;
}
/* End captions */
</pre>

以上这一段就是默认主题中新增的关于图片说明的样式代码.如果你正在使用的主题中没有对Caption做出定义的话,即便在编辑的时候加入了图片说明,这些文字也只能以普通的方式显示出来,等于是没有效果.

所以如果你想让图片说明起到作用,可以将上面的代码修改成自己喜欢的样式之后复制到主题的CSS文件中.

顺便提一下,Wordpress其中有4项比较重要的新功能:日志版本修订,一键发布标签,支持Google Gears缓存静态文件,主题预览.这四个里面日志版本修订对于团队博客来说也许有点用处,对于个人博客来说只会加重数据库的负担,<a title="屏蔽 WordPress 日志修订功能" href="http://fairyfish.net/2008/07/15/disable-post-revision/" target="_blank">屏蔽掉</a>最好.另外的Turbo和主题预览我都非常喜欢,很实用.

你升级到WP2.6了么?