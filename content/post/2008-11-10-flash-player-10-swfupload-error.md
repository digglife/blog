---
title: 升级Flash Player 10导致WordPress Flash上传工具失效
author: 摩摩诘
type: post
date: 2008-11-10T04:37:22+00:00
url: /articles/flash-player-10-swfupload-error.html
index_image:
  - https://www.digglife.net/wp-content/uploads/IndexImage/flash-wordpress.jpg
views:
  - 2051
bot_views:
  - 2163
dsq_thread_id:
  - 6893379
duoshuo_thread_id:
  - 1154125469839262118
categories:
  - 博客研究
tags:
  - flash
  - wordpress

---
这两天在后台上传图片时一直无法使用WordPress的Flash上传工具（[SWFUploader][1]），点击了Upload之后没有任何反应，只好暂时使用Browser Uploader。因为这个问题正好发生在重装了系统之后，所以怀疑是新安装的Flash Player 10的问题，搜索了一下之后发现[果然如此][2]。

<!--more-->

这是一个很古老的问题了，具体的原因是：Flash Player 10出于安全性的考量对调出文件浏览对话框的条件进行了升级，只有用户进行了直接性的交互操作才能激活文件浏览对话框，比如鼠标点击Flash上传按钮，这是为了防止恶意代码打开文件浏览窗口，可能会导致用户在无意中上传某些敏感信息给第三方服务器。

而WordPress的上传工具SWFUploader采取的是Flash+JavaScript组合，它的上传按钮只是一个HTML式的按钮，点击上传按钮后会激活一段JavaScript代码让Flash打开文件浏览窗口，在Flash看来这是一个间接操作，因此导致错误。

除了WordPress之外，这个问题还影响到Flick、Zooomr等图片/视频分享网站的上传操作。

目前[SWFUPloader的2.2.0版本][3]已经解决了这个问题，似乎采取的是直接使用Flash按钮的模式，避开了Flash Player的安全问题。不过WordPress里的SWFUPloader还没有升级到这个版本。WordPress 2.8的功能介绍中表示将会创建一个基于Flash 10的上传工具，估计等到2.8才会彻底解决这个问题。

现在解决这个问题要么从SWFUPloader下手，要么从Flash下手，所有有两种解决方案：

1.下载一个<a href="http://wordpress.org/support/topic/177127#post-886724" target="_blank">SWFUPloader补丁</a>，解压后覆盖原文件即可。

搞定后按钮变得很丑陋，不过只要功能OK，后台变丑也无所谓啦。如果实在看着不爽也可以自己修改一下images文件夹里面的那个png图片。

2.卸载Flash Player 10，安装Flash Player 9。

首先需要下载一个[官方的卸载工具][4]，然后下载Flash Player 9后安装即可。

 [1]: http://www.swfupload.org/
 [2]: http://www.bit-101.com/blog/?p=1382
 [3]: http://swfupload.org/forum/news/827
 [4]: http://kb.adobe.com/selfservice/viewContent.do?externalId=tn_14157 "Flash卸载工具"