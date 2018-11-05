---
title: 打造谷歌音乐桌面版
author: 摩摩诘
type: post
date: 2009-04-07T12:34:58+00:00
url: /articles/google-music-app.html
syntaxhighlighter_encoded:
  - 1
index_image:
  - https://www.digglife.net/wp-content/uploads/IndexImage/music.png
bot_views:
  - 3211
views:
  - 7443
duoshuo_thread_id:
  - 1154125469839262140
categories:
  - 谷歌相关
tags:
  - google
  - 网络程序
  - 谷歌音乐

---
刚刚发布不久的[谷歌音乐搜索][1]给我们提供了海量的正版音乐，歌曲码率普遍在192kbps以上，而且加载速度极快，配上那个简洁的播放器，实在是非常完美的音乐搜索引擎。我这些天想听音乐的时候都是直接用谷歌音乐播放器，体验非常不错，和本地播放基本上没有什么区别。

所以将谷歌的这个播放器桌面化之后，我们甚至可以扔掉现有的播放器。既然能够在保持和本地播放器相同体验的情况下免费享受到高品质的在线音乐，对于我这种没有收藏癖，而且对音质没有太大要求的人来说本地播放器和音乐就毫无意义了。

<!--more-->

做法很简单，只需要一个Chrome浏览器即可，当然，如果你记得[Mozilla神奇的三菱镜Prism][2]，也可以尝试这个能将网络程序桌面化的软件或者Firefox扩展。打开[谷歌音乐播放器链接][3]，然后点击Create Application Shortcut（Chrome）或者Convert Website To Application（Prism），生成桌面图标即可。

![谷歌音乐桌面版][4]

因为这个播放器网页是没有Favicon的，所以生成的Shortcut没有图标，不好看。这里提供两个PNG透明图标（32&#215;32大小），内附用[Toycon][5]制作的ico图标文件，大家[下载][6]后可以在图标属性里指定。感谢[Fisio][7]复刻的[Google Music Trend图标][8].

![谷歌音乐图标][9]

用Prism的好处在于可以将其最小化到系统托盘，而且能够显示指定的Favicon。而用Chrome的话，网页上的favicon还是一个白色方块。我查看了Gears数据文件夹下的permissions.db文件（路径：\Local Settings\Application Data\Google\Chrome\User Data\Default\Plugin Data\Google Gears），貌似是用Base64编码指定的Favicon，但是不知道如何更改，于是作罢。

如果你是Mac用户，还可以像Fisio同学那样，将其做成一个[Dashboard Widget][10]。

估计不久之后会出现[Adobe AIR][11]版本的，哈哈，网络程序桌面化势不可挡啊。

 [1]: http://www.google.cn/music/homepage
 [2]: https://www.digglife.net/articles/prism-extension.html "Prism扩展:将Web应用桌面化"
 [3]: http://g.top100.cn/7872775/html/player.html
 [4]: https://www.digglife.net/wp-content/uploads/archive/google-music-app.png
 [5]: https://www.digglife.net/articles/convert-image-icon-with-drag-drop.html "免费绿色的图片转ICO图标工具ToYcon"
 [6]: http://www.fileden.com/files/2008/11/6/2176503/Gmusic%20icons.zip "谷歌音乐图标文件下载"
 [7]: http://fisio.cn
 [8]: http://twitpic.com/2yazi
 [9]: https://www.digglife.net/wp-content/uploads/archive/gmusic-icons.png
 [10]: http://twitpic.com/2y9io
 [11]: https://www.digglife.net/articles/air-applications-for-bloggers.html
