---
title: 小技巧:使用Google Flash Player播放在线音乐
author: 摩摩诘
type: post
date: 2007-07-13T09:24:37+00:00
url: /articles/listen-mp3-with-google-flash-player.html
0:
  - bb9074143e6b5b17f410d3560c2de2b79aa34286183d1b7ac30e9b83b99dc60583fec3314906e2da83ed5d265ce980f8
  - bb9074143e6b5b17f410d3560c2de2b79aa34286183d1b7ac30e9b83b99dc60583fec3314906e2da83ed5d265ce980f8
1:
  - e953712c453905a06944141a7645171cebdf27be2a6fb66a37beaddfbb3086ec8fd157fa67adfe3a6b27b384cd5669dc
  - e953712c453905a06944141a7645171cebdf27be2a6fb66a37beaddfbb3086ec8fd157fa67adfe3a6b27b384cd5669dc
comment_count:
  - 2
related_posts:
  - 'a:2:{s:4:"time";i:1224890110;s:13:"related_posts";s:1371:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/google-apps-firefox-sidebar.html" title="集装:在Firefox侧边栏载入Google应用">集装:在Firefox侧边栏载入Google应用</a></li><li><a href="http://www.digglife.cn/articles/embed-presentation-google-docs.html" title="Google在线演示文稿新增网页嵌入功能">Google在线演示文稿新增网页嵌入功能</a></li><li><a href="http://www.digglife.cn/articles/adobe-media-player-beta.html" title="Adobe将于今日正式发布Adobe Media Player Beta">Adobe将于今日正式发布Adobe Media Player Beta</a></li><li><a href="http://www.digglife.cn/articles/google-presentation-competition.html" title="细数Google在线演示文稿的竞争对手">细数Google在线演示文稿的竞争对手</a></li><li><a href="http://www.digglife.cn/articles/custom-flv-video-player.html" title="给博客打造个性化的FLV视频播放器.">给博客打造个性化的FLV视频播放器.</a></li><li><a href="http://www.digglife.cn/articles/view-original-articles-inside-google-reader.html" title="在Google Reader内部查看Feed原文">在Google Reader内部查看Feed原文</a></li><li><a href="http://www.digglife.cn/articles/10-clever-tricks-of-google-search.html" title="值得了解的7个Google搜索技巧">值得了解的7个Google搜索技巧</a></li></ul>";}'
bot_views:
  - 2114
views:
  - 1829
duoshuo_thread_id:
  - 1154125469839261844
categories:
  - 谷歌相关
tags:
  - google
  - 在线程序
  - 播放器

---
WordPress下已经有漂亮强大的AudioPlayer了,但是Google的这个主要为Gmail的MP3附件设计的播放器也不错.在博客中插入MP3文件时,这个Flash播放器也是个不错的选择.

方法很简单,记下下面的一段代码就可以了:注意将[MP3_file]替换成你的MP3连接.

> <embed type=&#8221;application/x-shockwave-flash&#8221; wmode=&#8221;transparent&#8221; src=&#8221;<a href="http://mail.google.com/mail/html/audio.swf?audioUrl=%5BMP3_file%5D" onclick="return top.js.OpenExtLink(window,event,this)" target="_blank">http://mail.google.com/mail<wbr></wbr>/html/audio.swf?audioUrl=[MP3<wbr></wbr>_file]</a>&#8221; height=&#8221;27&#8243; width=&#8221;320&#8243;></embed>

下面这个是来自Linkin Park重新演绎的变形金刚主题曲.
  


<embed src="http://mail.google.com/mail/html/audio.swf?audioUrl=http://www.slashfilm.com/wp/wp-content/interviews/transformerstheme.mp3%3Cbr%3E%3C/embed%3E" type="application/x-shockwave-flash" wmode="transparent" height="27" width="320">
</embed>


  
如果还想使用这个播放器播放任何在线MP3文件,可以安装<a href="http://lifehacker.com/assets/resources/2006/08/google-player.user.js" target="_blank">一个Greasemonkey代码</a>(必须在安装有<a href="http://www.greasespot.net/" target="_blank">Greasemonkey</a>的Firefox下安装),它会在每一个MP3链接旁显示该播放器.
  
[<img src="https://www.digglife.net/wp-content/uploads/3/379/2007/07/embeddedgoogleplayer5-thumb.png" style="border-width: 0px" alt="embeddedgoogleplayer5" border="0" height="121" width="240" />][1]

 [1]: https://www.digglife.net/wp-content/uploads/3/379/2007/07/embeddedgoogleplayer5.png "embedded-google-player.png"
