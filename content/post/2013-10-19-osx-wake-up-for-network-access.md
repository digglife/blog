---
title: OS X唤醒以供网络访问和本地下载的关系
author: 摩摩诘
type: post
date: 2013-10-19T07:41:28+00:00
excerpt: 很多人在网上问，如何在有下载任务的时候让Mac保持唤醒，不自动进入休眠模式呢？不少人都信誓旦旦地表示，在OS X的节能器设置中勾选“唤醒以供网络访问”能够达到这个目的，最近在某乎上还是看到有很多人这么回答，所以忍不住要澄清一下。
url: /articles/osx-wake-up-for-network-access.html
duoshuo_thread_id:
  - 1154125469839262166
index_image:
  - https://www.digglife.net/wp-content/uploads/2013/10/mac-wake-from-sleep.jpg
views:
  - 2247
categories:
  - Mac学习
tags:
  - mac
  - OSX
  - 苹果

---
很多人在网上问，如何在有下载任务的时候让Mac保持唤醒，不自动进入休眠模式呢？不少人都信誓旦旦地表示，在OS X的节能器设置中勾选“唤醒以供网络访问”能够达到这个目的，最近在某乎上还是看到有很多人这么回答，所以忍不住要澄清一下。

总而言之，节能器中“唤醒以供网络访问”和本地下载毫无关系，“唤醒以供网络访问”的主要功用是局域网内共享，需要和 Bonjour Sleep Proxy 配合适用。

而如果想在下载的时候避免Mac进入睡眠，唯一的方式是，在节能器中关闭睡眠。

&nbsp;

<!--more-->

### “唤醒以供网络访问”和本地下载毫无关系

“<a title="关于“请求时唤醒”和 Bonjour Sleep Proxy" href="http://support.apple.com/kb/HT3774?viewlocale=zh_CN" target="_blank">唤醒以供网络访问</a>”的确是一个在字面上容易引起误会的描述，这句话真正的意思是，当外部试图以某种方式连接这台 Mac 时，OS X 会从睡眠模式中唤醒以供外部访问。主要的使用场景包括但不仅限于：iTunes 家庭共享（比如用 iPad 远程访问 OS X 的 iTunes 资料库） ，SSH 访问，文件共享等等。这些和本地的下载任务都没有半毛钱关系。

### “唤醒以供网络访问”需要和Bonjour Sleep Proxy配合使用

按需唤醒Mac，听起来好智能好环保的感觉是吧？别开心，这功能也不是说你想连就连得上。如果你的家庭局域网里没有<a title="Airport" href="http://www.apple.com/compare-wifi-models/" target="_blank">Airport基站</a>、<a title="Airport Time Capsule" href="http://www.apple.com/cn/airport-time-capsule/" target="_blank">Time Capsule</a>或者<a title="Apple TV" href="http://www.apple.com/appletv/" target="_blank">Apple  TV</a>，这个功能是不起作用的。

> 网络上所有在“节能器”偏好设置中启用了“请求时唤醒”功能的 Mac 将自行注册，并注册其共享的服务以与 Bonjour Sleep Proxy 配合使用。请求访问处于睡眠状态的 Mac 上的共享服务时，<a title="Bonjour_Sleep_Proxy" href="http://en.wikipedia.org/wiki/Bonjour_Sleep_Proxy" target="_blank">Bonjour Sleep Proxy </a>会唤醒该 Mac 来处理此请求。请求完成后，Mac 将再次注册与 Bonjour Sleep Proxy 配合使用，并在“节能器”偏好设置中定义的睡眠间隔时间内重新进入睡眠状态。

也就是说，如果你只是通过普通路由组建局域网，而没有任何可以作为Bonjour Sleep Proxy工作的设备的话，开启了这个选项也没法使用。

### 如何在下载时避免Mac进入睡眠

那么如果我有大量下载任务时怎么办呢？唯一的方法是，在节能器里关闭睡眠，然后使用下载工具（如<a title="迅雷Mac版" href="http://mac.xunlei.com/" target="_blank">迅雷Mac版</a>）的“下载完成后关机（睡眠）”之类的功能。

<img alt="Mac永不睡眠" src="https://www.digglife.net/wp-content/uploads/2013/10/never-sleep.png" width="500" height="398" />

总之，“唤醒以供网络访问”和本地下载是毫无关系的。
