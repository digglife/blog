---
title: 解决QQ音乐网页版在Ubuntu Firefox下无法播放的问题
author: 摩摩诘
type: post
date: 2014-07-05T13:50:44+00:00
excerpt: 一贯无视 Linux 平台的腾讯理所当然地没有开发QQ音乐Linux版，于是想尝试QQ音乐网页版，结果发现歌曲无法播放。更换到 Chrome 下访问QQ音乐播放却毫无压力，切换回Firefox，祭出开发者工具，查看控制台log的发现了症结——“Content Type”中的“Audio/mp4”不支持。腾讯原来已经向水果看齐换上了高大上的AAC，实在是意外的发现，点赞。
url: /articles/fix-qq-music-web-player-ubuntu-firefox.html
index_image:
  - https://www.digglife.net/wp-content/uploads/2014/07/qq-music.png
duoshuo_thread_id:
  - 1154125469839262183
views:
  - 1270
categories:
  - Ubuntu技巧
tags:
  - Linux
  - qq
  - ubuntu
  - 火狐技巧

---
这个月响应海外IT部门的号召，工作用机从 Windows 7 迁移到了定制版的 Ubuntu 14.04。因为公司的软件对 Linux 有几乎100%的覆盖率，有的客户端软件新版甚至在 Linux 平台首发，提供比 Windows 更良好的支持，所以办公上毫无痛感。问题是平时私人用到的一些软件和服务，比如QQ音乐。

一贯无视 Linux 平台的腾讯（无贬义）理所当然地没有开发QQ音乐Linux版，于是想尝试QQ音乐网页版，结果发现歌曲无法播放。刚开始以为是腾讯还在网页版上用万恶的 Windows Media Player 插件，但是随即发现 Firefox 插件列表里 WMP 赫然在列，于是排除。尝试更换到 Chrome 下访问QQ音乐播放毫无压力，呵呵，尼玛坑我呢。切换回Firefox，祭出开发者工具，查看控制台log的发现了症结——“Content Type”中的“Audio/mp4”不支持。腾讯原来已经向苹果看齐换上了高大上的AAC，实在是意外的发现，给点赞。既然不支持解码AAC，那么安装一个好了。
  
<!--more-->

<img class="alignnone size-medium wp-image-3816" src="http://digglife.qiniudn.com/wp-content/uploads/2014/07/qmusic-m4a-500x170.png" alt="Ubuntu下的Firefox无法解码QQ音乐提供的AAC编码的m4a音频文件" width="500" height="170" />

一条命令可以安装大多数音视频解码器：

`sudo apt-get install ubuntu-restricted-extras`

安装完毕，重启 Firefox，问题解决。

<a href="https://help.ubuntu.com/community/RestrictedFormats" title="Ubuntu 涉及到专利和版权的媒体格式" target="_blank">Ubuntu 为了规避专利和版权问题</a>，很多东西没有预装，比如和这个问题相关的解码器。那么为什么明明 Ubuntu 上没有AAC解码器， Chrome 却可以正常播放呢，自然的想法是 Chrome 夹藏私货。Google一下，果然 <a title="Chrome内置音视频解码器" href="http://www.chromium.org/audio-video" target="_blank">Chrome 内置有一批解码器</a>，包括AAC。其实和Ubuntu 一样，开源的 Chromium 同样规避了 MP3/AAC/H.264等 解码器，只是在 Google 私有的 Chrome 里内置了这些，正强推的Chrome OS 则内置了更多。

另，QQ音乐是目前唯一一个我日常使用的腾讯服务，而且开了年费绿钻。原本只是因为曲库够全，各个平台的客户端体验拔群才喜欢的，现在发现网页版的体验也非常棒，仅不依赖 Flash 这一点对我来说就完爆虾米之类。赞！