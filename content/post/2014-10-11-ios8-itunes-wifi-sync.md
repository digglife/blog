---
title: 解决iOS 8无法使用iTunes WiFi同步的问题
author: 摩摩诘
type: post
date: 2014-10-11T13:09:51+00:00
excerpt: 自己的 iPhone/iPad 在升级到 iOS 8 之后双双无法通过 WiFi 和 iTunes 同步了，显然这又是 iOS 8 众多 Bug 中的一个。平时我添加音乐和电子书都直接用 WiFi 同步，习惯了之后要我接数据线实在不能忍，何况还是两台。好在最终发现解决这个问题不用等苹果发补丁，自己就能搞定。
url: /articles/ios8-itunes-wifi-sync.html
views:
  - 2395
duoshuo_thread_id:
  - 1154125469839262199
index_image:
  - https://www.digglife.net/wp-content/uploads/2014/10/ios-wifi-sync.png
categories:
  - Mac学习
tags:
  - ios
  - ipad
  - iphone
  - itunes
  - 同步

---
自己的 iPhone/iPad 在升级到 [iOS][1] 8 之后双双无法通过 WiFi 和 iTunes 同步了，显然这又是 iOS 8 众多 Bug 中的一个。平时我添加音乐和电子书都直接用 WiFi 同步，习惯了之后要我接数据线实在不能忍，何况还是两台。好在最终发现解决这个问题不用等苹果发补丁，自己就能搞定。

<!--more-->

### 如何修复 WiFi 同步

直觉上这种问题应该和网络设定有关，所以尝试了一下恢复网络出厂设置。虽然有几个 WiFi 密码和 VPN 设置也会被抹掉，但是无所谓了。

  1. 还原 iOS 设备的网络设置
逐步导航到 `设置 - 通用 - 还原 - 还原网络设置`，然后输入密码，点击 还原网络设置，系统会自动重启。

<img src="http://digglife.qiniudn.com/wp-content/uploads/2014/10/ios8-reset-network-settings-500x413.png" alt="iOS8还原网络设置" width="500" height="413" class="alignnone size-medium wp-image-3926" />

  2. 用数据线连接到PC
重置网络设置之后，我发现“关于本机” 里的 “名称” 会重置成默认的 iPhone 或者 iPad，这也不奇怪，UNIX 系统的网络设置本来也理所应当包括 Hostname，另外 iTunes 和 iOS 设备之间的信任关系也解除了。所以要让 WiFi 同步重新运作，需要先用数据线连接信任电脑。事前最好重启一下 iTunes。

<div id="attachment_3925" style="width: 551px" class="wp-caption alignnone">
  <img src="http://digglife.qiniudn.com/wp-content/uploads/2014/10/ios8-trust-pc.jpg" alt="iPhone/iPad信任电脑" width="541" height="277" class="size-full wp-image-3925" />
  
  <p class="wp-caption-text">
    iOS 8 重置网络设置之后需要重新信任电脑
  </p>
</div>

  3. （同步后）拔掉数据线
拔掉数据线之后，如果iTunes里设备标签下的 iPhone/iPad 的图标没有消失，那么 WiFi 同步就可以正常运作了。 </ol> 

### 可能影响 Wi-Fi 同步的其他问题

我搜了一下，貌似还有不少人有其他的原因，解决方式无外乎以下几个，但是我觉得这些都属于误中副车而已。

  * 重启电脑
  * 删除 WiFi 热点，然后重新加入
  * 关闭iOS 上的 Hands Off

### 关于 WiFi 同步需要在充电状态的误解

无论是官方文档，还是 iOS 系统中有关 WiFi 同步的描述，都提到需要插入电源。原文是“iPhone/iPad 插入电源并接入 WiFi 时，与电脑上的 iTunes 自动同步”。

<img src="http://digglife.qiniudn.com/wp-content/uploads/2014/10/wifi-sync-charge.png" alt="iTuns WiFi 同步设定" width="500" height="361" class="alignnone size-full wp-image-3927" />

而事实上，iTunes WiFi 同步是**不需要**在充电状态下的，至少从 iOS 7 开始就是这样了。本来这个前提条件也是很扯淡的，为什么通过 WiFi 传一下数据还需要插电呢，我就喜欢耗电，你咬我啊。可能这个功能刚推出的时候需要插电，我也依稀有这个印象，但是后来把这个条件去掉了，而系统中的说明文本都没改。类似这种系统说明文字带来的误解，OS X 上也有个经典的“[唤醒以供网络访问][2]”。

虽然一个大版本升级难免有各种各样的问题，但是 iOS 8 这次真的是槽点太多了，也难怪大家都在抱怨。目测一周后即将正式推出的 Yosemite 会被吐得更厉害，坐等中外毒舌。

 [1]: https://www.digglife.net/articles/tag/ios "DiggLife iOS相关文章"
 [2]: https://www.digglife.net/articles/osx-wake-up-for-network-access.html "OS X唤醒以供网络访问和本地下载的关系"