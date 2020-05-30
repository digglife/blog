---
author: 摩摩诘
categories:
- 代码卷轴
date: 2020-05-29T22:44:00+08:00
tags:
- 游戏
- ps4
- 最终幻想7
- python
title: 最终幻想 7 重制版原声带下载(8CD)
url: /articles/final-fantasy-vii-ost.html

---
最终幻想 7 重制版原声带前几天正式推出了，有 8 张 CD，可谓豪华，但是截止到今天，我还没看到任何一家音乐流媒体平台上线这套 OST，于是在 Youtube 上搜了一下，发现有人已经上传了这套近 9 个小时的原声音乐，于是祭出之前[为 荒野大镖客2 写的 Python 脚本](https://www.digglife.net/articles/red-dead-redemption-2-ost.html)，制作了一个 MP3 专辑版。

<!--more-->

受限于 Youtube 的来源，最终 MP3 的码率为 128 kbps，按如今的标准是低了些。在真正的数字版出现之前，也只能权当尝鲜了。

```
Input #0, mp3, from '/Users/zhu/Downloads/01. The Prelude - Reunion.mp3':
  Metadata:
    album           : FINAL FANTASY VII REMAKE Original Soundtrack
    genre           : Soundtrack
    date            : 2020
    title           : 01. The Prelude - Reunion
    artist          : Nobuno Uematsu
    album_artist    : Nobuno Uematsu
    disc            : 01
    track           : 01
    encoder         : Lavf58.29.100
  Duration: 00:03:24.02, start: 0.023021, bitrate: 129 kb/s
    Stream #0:0: Audio: mp3, 48000 Hz, stereo, fltp, 128 kb/s
    Metadata:
      encoder         : Lavf
    Stream #0:1: Video: mjpeg (Baseline), yuvj420p(pc, bt470bg/unknown/unknown), 1280x1280 [SAR 1:1 DAR 1:1], 90k tbr, 90k tbn, 90k tbc (attached pic)
    Metadata:
      title           : ALBUM_COVER
      comment         : Cover (front)
```

![最终幻想7重制版原声带](/wp-content/uploads/ffvii-ost.png)

因为这次的时间线包含有 CD 序号信息，所以稍微修改了一下此前的脚本，让其能识别并写入 CD 序号信息。

最终幻想7重制版原声带共 8CD，180 个 MP3 文件，百度盘下载地址如下。

[最终幻想7重制版原声音乐下载](https://pan.baidu.com/s/11hCQZCXMrCS0535TdTubaw) | 提取码: `dvrb`

