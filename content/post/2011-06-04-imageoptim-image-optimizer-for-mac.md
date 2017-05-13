---
title: Mac OS X下的图片压缩软件ImageOptim
author: 摩摩诘
type: post
date: 2011-06-04T10:46:49+00:00
excerpt: 最近几天用 Page Speed 优化博客速度的时候发现，有好多图片有压缩的潜力，而且 Page Speed提供的参考图片压缩比都很高，所以根据 Google 的建议找了几个图片压缩工具。其中Mac下的ImageOptim内置了6种压缩算法，有着很高的压缩比。操作起来也非常简单，拖拽需要压缩的图片到 ImageOptim窗口即开始压缩，甚至不需要按其他按钮。
url: /articles/imageoptim-image-optimizer-for-mac.html
index_image:
  - https://www.digglife.net/wp-content/uploads/2011/06/imageoptim-index.png
views:
  - 3145
bot_views:
  - 27
duoshuo_thread_id:
  - 1154125469839262152
categories:
  - Mac学习
tags:
  - mac
  - 图片压缩
  - 图片处理

---
最近几天用 [Page Speed][1] 优化博客速度的时候发现，有好多图片有压缩的潜力，而且 Page Speed提供的参考图片压缩比都很高，所以[根据 Google 的建议][2]找了几个图片压缩工具，比如适合 JPEG 的 jpegoptim 和 jpegtran，适合PNG图片的 OptPNG 和 PNGOUT 等，这些压缩工具都提供了丰富的命令行接口，使用起来灵活性非常大。

<!--more-->

[OptiPNG][3] 的主页介绍了一款有图形界面的 Mac 软件 [ImageOptim][4]，内置有包括上面提到的4种在内的6种压缩算法，用户可以根据自己的需要选择。操作起来也非常简单，拖拽需要压缩的图片到 ImageOptim窗口即开始压缩，甚至不需要按其他按钮。

<img src="http://digglife.qiniudn.com/wp-content/uploads/2011/06/imageoptim.png" alt="ImageOptim的图形界面" width="600" height="284" />

ImageOptim默认会用压缩后的图片覆盖原图片，如果希望保留备份，可以在“偏好设置”里更改。此外，为了达到最佳压缩想过，ImageOptim 会用已经勾选的压缩工具逐个压缩对象图片，所以如果无法接收最终图片的质量，可以酌情去掉几个压缩工具。如上图就有肉眼可感的损失。

<img src="http://digglife.qiniudn.com/wp-content/uploads/2011/06/imageoptim-preferences.png" alt="ImageOptim的偏好设置" width="600" height="364" />

这两天使用下来觉得压缩比还是非常高的，苹果自带的截图工具可能为了保证图片质量，生成的PNG图片普遍很大，所以有非常可观的压缩空间。在经过神器全开的ImageOptim压缩之后，Google 的 Page Speed 依然提示图片有压缩的可能，真不知道Google采用的是神马压缩算法。

此外，在图片方面提高网站的整体载入速度还有很多地方需要注意，比如在img标签中指定好图片的长宽，同一张图片需要显示为几种大小时尽量提供不同的版本而不是通过CSS来控制等等。

[ImageOptim主页][4]

 [1]: http://pagespeed.googlelabs.com/
 [2]: http://code.google.com/speed/page-speed/docs/payload.html#CompressImages
 [3]: http://optipng.sourceforge.net/
 [4]: http://imageoptim.pornel.net/