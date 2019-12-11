---
author: 摩摩诘
categories:
- 代码卷轴
date: 2019-12-11T15:37:00+08:00
tags:
- 电影
- 字幕
title: 如何解决 HDR 模式下字幕太亮的问题
url: /articles/hdr-subtitle-too-bright.html

---
自从买了 Bravia X9000F，我就常在 Kodi 上看各种「来历不明」的 4K HDR 电影，效果虽然拔群，但是 HDR 模式下经常会碰到字幕太亮的问题，一来白光闪瞎眼，二来字幕会「漏光」，非常影响暗色画面的观感。

<!--more-->

## 为什么会有「字幕漏光」的问题

其实「字幕漏光」是我生造的词语，意思就是不仅字幕超亮，字幕周围的一大块区域都会变亮，如果恰好是一个黑色画面，溢出感就很明显，如果开了 HDR，就会更加明显。

我用手机拍了一下，注意下图中字幕周围的黑边变化。

![Blade Runner 2049 Subtitle Too Bright](/wp-content/uploads/blade_runner_subtitle_too_bright.gif)

其实造成这个问题的原因很简单，就是一些电视（比如索尼和三星的中高端）的所谓「自动局部光控调节技术」，会通过调节屏幕各个部分的亮度优化对比度。这个功能用于电影图像本身能提升观影体验，让暗部更暗，亮部更亮，但是字幕根本不属于图像的一部分，所以针对横穿画面的字符进行亮度调节就会影响字幕周围的画面。

那么有人说，关掉这个局部光控技术不就好了。当然不好，这个功能明明能提高观影体验，关了岂不是辜负了技术开发人员的苦心？

## 蓝光电影光盘内置字幕的颜色

其实白色字幕太晃眼这个问题，或许电影发行方已经想到了，因为如今蓝光电影光盘里的 PGS 字幕[^1]，很多前景色都并不是白色，而是灰色。用灰色字幕，不仅不晃眼，恰好因为不够白，也不会触发电视的局部背光增强功能。是的，答案就这么简单。

下图就是内置 PGS 字幕的样式，注意和默认样式下的 SRT 字幕的对比。截图有压缩。

![Blade Runner 2049 PGS Subtitle](/wp-content/uploads/blade_runner_2049_pgs_subtitle.png)

![Blade Runner 2049 SRT Subtitle](/wp-content/uploads/blade_runner_2049_srt_subtitle.png)


可是，就好像口红一样，「灰色」这个色号有太多种了，如今蓝光光盘里的 PGS 字幕颜色的 RGB 精确值到底是多少呢？

我用播放器截图之后，用 macOS 自带的「数码测色计」看了一下，答案是 RGB **`(154, 154, 154)`**, 也就是 HEX **`#9a9a9a`**。

Window 或 Linux 用户可以直接把图片拖进 Chrome/Firefox，用开发者工具里的「拾色器」查看。

有了这个颜色，我们在播放器对普通文本格式的字幕做相应的配置即可。然而 Kodi 似乎不支持自定义字幕色彩，所以我做了一番调查似乎也没什么卵用。😂

## 根本解决方式

说到底，局部控光技术产生的根本原因，还是 LCD 需要「背光灯」才能亮。所以要根本解决这种问题，直接买一台 OLED 就好了，像素级别控光，就不用什么根据画面调整背光亮度了。

截止到目前为止，最具性价比的应该是 2018 年的 OLED 次旗舰 [SONY Bravia A8F](https://www.sony.com.hk/zh/electronics/televisions/a8f-series/specifications)。

[^1]: PGS，Presentation Graphic Stream，是蓝光电影的标准字幕文件，顾名思义，这是一种图形格式的字幕。有兴趣的可以参见[专利文档](https://patents.google.com/patent/CN101702757B/zh)。
