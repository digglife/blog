---
title: OS X 终于能自动切换耳机和HDMI输出了
author: 摩摩诘
type: post
date: 2014-10-24T15:19:26+00:00
excerpt: 还是没忍住升级到了 OS X Yostemite，除了图标让我感觉很脏乱之外，好像也找不到什么不升级的理由。今天发现 Yosemite 的一个意外的小改进，音频的耳机输出和 HDMI 输出终于能够自动切换了。
url: /articles/osx-headphone-hdmi-audio-output.html
index_image:
  - https://www.digglife.net/wp-content/uploads/2014/10/hdmi.png
views:
  - 1050
duoshuo_thread_id:
  - 1154125469839262200
categories:
  - Mac学习
tags:
  - hdmi
  - mac
  - OSX

---
还是没忍住升级到了 OS X Yostemite，除了图标让我感觉很脏乱之外，好像也找不到什么不升级的理由。今天发现 Yosemite 的一个意外的小改进，音频的耳机输出和 HDMI 输出终于能够自动切换了。用 MBP 的都知道，耳机插入的时候，音频输出会自动从外放切换过来，而且音量还会自动调整。

<!--more-->

然而在 Yosemite 之前，如果 Macbook 使用 HDMI 和外置显示器连接，且同时输出音视频，当插入耳机到 Macbook 内置接口时，声音输出不会自动切换到耳机，需要到 用户偏好设置 中手动切换，非常不便。估计苹果的码农们也意识到这是个问题，所以终于在 Yosemite 里改过来了。这个 Bug Fix 不得不赞，对我来说这种小修正比什么 Hands Off 什么花里胡哨的新功能要实在。

<img src="https://www.digglife.net/wp-content/uploads/2014/10/osx-hdmi-audio-output-500x390.png" alt="OSX 选择音频输出设备" width="500" height="390" class="alignnone size-medium wp-image-3934" />

但是。
  
但是啊。

这个贴心的 Bug Fix 催生出了一个全新的 Bug。插入耳机的瞬间，音频的确会自动从 HDMI 切换过来，可是当显示器从睡眠状态唤醒的时候，即便耳机还插着，音频还是会自动输出到 HDMI。这显然不合逻辑，既然内置外放在耳机插入的时候会一直处于屏蔽状态，没理由 HDMI 的行为会特殊化。这样每次点亮显示器，我还是得手动切换，要不就得把耳机重新插拔一次。我猜想系统有一个全局的Listner，音频输出到哪里是根据接口的激活顺序来的，耳机接口和HDMI接口哪个后激活音频就输出到哪里。本来是一个比较自然的设定，只是在这里就不太人性化了。

不过 Bug 修复产生新 Bug 是码农世界的常态，何况苹果在软件方面的执念似乎也大不如前了。可叹。
