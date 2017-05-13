---
title: 给博客打造个性化的FLV视频播放器.
author: 摩摩诘
type: post
date: 2007-07-29T08:59:35+00:00
url: /articles/custom-flv-video-player.html
0:
  - 6bc67beb6c5f4a9007c913494d6768ab8eaf59c52dcb1605789fcd0c3ba1c65c594bf1d2b1a8dfbc16618dbe379c258c
  - 6bc67beb6c5f4a9007c913494d6768ab8eaf59c52dcb1605789fcd0c3ba1c65c594bf1d2b1a8dfbc16618dbe379c258c
1:
  - be893b63e336a92308a6dcd627fc4fcc426a0f7ece827007e40bb407516c942cbb920ddb15066124db143b676b0ce874
  - be893b63e336a92308a6dcd627fc4fcc426a0f7ece827007e40bb407516c942cbb920ddb15066124db143b676b0ce874
comment_count:
  - 3
related_posts:
  - 'a:2:{s:4:"time";i:1224880533;s:13:"related_posts";s:1388:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/adobe-media-player-beta.html" title="Adobe将于今日正式发布Adobe Media Player Beta">Adobe将于今日正式发布Adobe Media Player Beta</a></li><li><a href="http://www.digglife.cn/articles/listen-mp3-with-google-flash-player.html" title="小技巧:使用Google Flash Player播放在线音乐">小技巧:使用Google Flash Player播放在线音乐</a></li><li><a href="http://www.digglife.cn/articles/%e8%b6%85%e7%ba%a7%e9%9b%86%e8%a3%85%e7%ae%b1%e4%b8%8b%e8%bd%bdyoutube%e8%a7%86%e9%a2%91%e7%9a%8423%e7%a7%8d%e6%96%b9%e5%bc%8f.html" title="超级集装箱:下载YouTube视频的23种方式">超级集装箱:下载YouTube视频的23种方式</a></li><li><a href="http://www.digglife.cn/articles/enhance-mobile-phone-pics.html" title="如何提高手机照片的质量">如何提高手机照片的质量</a></li><li><a href="http://www.digglife.cn/articles/improve-your-image-online.html" title="在线一键优化你的照片">在线一键优化你的照片</a></li><li><a href="http://www.digglife.cn/articles/prism-extension.html" title="Prism扩展:将Web应用桌面化">Prism扩展:将Web应用桌面化</a></li><li><a href="http://www.digglife.cn/articles/online-image-resizer-cropper.html" title="15个在线图片缩放剪切工具">15个在线图片缩放剪切工具</a></li></ul>";}'
views:
  - 1123
bot_views:
  - 1946
duoshuo_thread_id:
  - 1154125469839261861
categories:
  - 酷软推荐
tags:
  - 博客工具
  - 在线程序
  - 播放器
  - 视频

---
<a href="https://www.digglife.net/wp-content/uploads/3/379/2007/07/unleashedstream1.png" atomicselection="true"><img height="41" alt="unleashedstream" src="http://digglife.qiniudn.com/wp-content/uploads/3/379/2007/07/unleashedstream-thumb.png" width="240" align="right" /></a>前不久YouTube推出了个性化播放器功能,但是给的修改选项太少,和默认的相比也没有多大的改变.<a href="http://www.unleashedstream.com" target="_blank">Unleashed Stream</a>则提供了一个更加自由的解决方案,你甚至可以给Flv视频烙上自己的Logo,而且你只需找到该Flv视频的Url就可以了.

**&nbsp;如何使用:**

和YouTube等网站上可以直接得到嵌入代码相比,这个自定义过程可能在开始稍微复杂一点,不过如果你只想简单地自定义的话,还是很简单的.

首先你需要在Unleashed Stream的网站上从四个播放器模式中选择一个,这里以**<a href="http://www.unleashedstream.com/index.php?option=com_content&task=view&id=3&Itemid=7" target="_blank">FLV Player 1</a>**为例,下面是使用代码:

> http://www.unleashedstream.com/flv1.swf?file=**http://sample.com/file.flv  
>** &logo=<u>http://yourlogo.png</u>

<!--more-->

上面的代码中**file=**后的黑体URL为flv视频地址,**logo=**后面的下划线URL可以替换为Logo地址(PNG格式).为了得到视频的Flv链接,我们可以使用<a href="http://keepvid.com/" target="_blank">Keepvid</a>或者国内常用的<a href="http://www.greendown.cn/soft/4625.html" target="_blank">UUmeFlvSpy</a>.得到链接后我们就可以替换以上提到的两个URL了.

比如下面是一个Compiz Fusion插件的视频

<embed src="http://www.unleashedstream.com/flv1.swf?file=http://player0046.tudou.com/flv/007/932/425/7932425.flv&logo=&logo=https://www.digglife.net/wp-content/uploads/3/379/2007/07/logo1.png" width="400" height="320" type="application/x-shockwave-flash" wmode="transparent">
</embed>

代码:

> <embed src=&#8221;http://www.unleashedstream.com/flv1.swf?file=http://player0046.tudou.com/flv/007/932/425/7932425.flv  
> &logo=https://www.digglife.net/wp-content/uploads/3/379/2007/07/logo1.png&#8221;  
> width=&#8221;400&#8243; height=&#8221;320&#8243; type=&#8221;application/x-shockwave-flash&#8221; wmode=&#8221;transparent&#8221;>

Ubleash Stream提供了非常多的自定义参数,上面只是一个简单的例子而已.