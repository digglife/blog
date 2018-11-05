---
title: 惊叹!在Linux命令行模式下看YouTube视频.
author: 摩摩诘
type: post
date: 2007-06-30T11:02:07+00:00
url: /articles/watch-youtube-video-under-linux-commandline.html
0:
  - 42d7e8460508f626cbae62932aade9f569895948db7ac85e6db22a160b70a2cf8317e8bd3f9b10ecb5f47c0ca7236096
  - 42d7e8460508f626cbae62932aade9f569895948db7ac85e6db22a160b70a2cf8317e8bd3f9b10ecb5f47c0ca7236096
comment_count:
  - 1
related_posts:
  - 'a:2:{s:4:"time";i:1224855882;s:13:"related_posts";s:1457:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/custom-preview-image-of-youtube-videos.html" title="自定义Youtube视频预览图">自定义Youtube视频预览图</a></li><li><a href="http://www.digglife.cn/articles/%e8%b6%85%e7%ba%a7%e9%9b%86%e8%a3%85%e7%ae%b1%e4%b8%8b%e8%bd%bdyoutube%e8%a7%86%e9%a2%91%e7%9a%8423%e7%a7%8d%e6%96%b9%e5%bc%8f.html" title="超级集装箱:下载YouTube视频的23种方式">超级集装箱:下载YouTube视频的23种方式</a></li><li><a href="http://www.digglife.cn/articles/picture-textaizer-ascii-art.html" title="将普通图片转换为字符或ASCII码拼图">将普通图片转换为字符或ASCII码拼图</a></li><li><a href="http://www.digglife.cn/articles/windows-linux-file-system.html" title="4款免费软件让你在Windows下访问Linux文件系统">4款免费软件让你在Windows下访问Linux文件系统</a></li><li><a href="http://www.digglife.cn/articles/how-to-install-kde40-in-ubuntu.html" title="如何在Ubuntu 7.10下安装KDE 4.0">如何在Ubuntu 7.10下安装KDE 4.0</a></li><li><a href="http://www.digglife.cn/articles/access-to-your-linux-files-from-windows.html" title="在Windows下访问Linux文件系统:Linux Reader">在Windows下访问Linux文件系统:Linux Reader</a></li><li><a href="http://www.digglife.cn/articles/gmail-video-final-cut.html" title="Gmail官方宣传片最终版出炉">Gmail官方宣传片最终版出炉</a></li></ul>";}'
bot_views:
  - 1827
views:
  - 1728
duoshuo_thread_id:
  - 1154125469839261831
categories:
  - 业界新闻
tags:
  - ASCII
  - Linux
  - text
  - Youtube
  - 命令行
  - 视频

---
如果经常上网,你一定见过ASCII码形式的图片,或许你还自己制作过放到QQ说明里面.但是你见过ASCII码形式的视频么.美国的<a target="_blank" href="http://hackedgadgets.com">hackedgadgets</a>发布了一段在Linux命令行模式下观看Youtube视频的实现方法,并附带了操作视频.

该操作系统是<a target="_blank" href="http://fedoraproject.org/">Linux Feroda 6</a>,他使用<a target="_blank" href="http://lynx.isc.org/lynx2.8.5/index.html">基于文本的Lynx浏览器</a>在YouTube上搜索视频,然后从网页源码中找到了下载视频需要的字符窜(大致相当于我们使用Flvspy等软件实现的效果).下载后调用Lynx浏览器的Shell启动Mplayer播放视频.我完全不知道Mplayer没有找到X环境的话还居然会自动调用一个文本引擎来解码.实在是太神奇了.

**截图**:(看的不是很清楚,但是大致的轮廓和动作都能够知道.嗯,这应该是个黑人说唱歌手的MV)

![youtube_text][1]

<!--more-->

镜头拉近后看到的全是字符.这不禁让我想起了Matrix.

![Zoom_in][2]

**YouTube视频:(作者戏称其为Data Stream)**

<p style="display: inline; float: none; margin: 0px; padding: 0px" contentEditable="false" id="53357c8b-5919-4e32-8c25-305d27c17a37:0f395c4a-cf0d-42ca-aef2-cdb63ce438c3" class="wlWriterSmartContent">
  <embed wmode="transparent" height="350" width="425" src="http://www.youtube.com/v/ji0A3kOAc9U">
  </embed>
</p>

[YouTube &#8211; Data Stream][3]

 [1]: https://www.digglife.net/wp-content/uploads/3/379/2007/06/youtube-text.png
 [2]: https://www.digglife.net/wp-content/uploads/3/379/2007/06/zoom-in.png
 [3]: http://www.youtube.com/watch?v=ji0A3kOAc9U
