---
title: 让Windows 8.1 支持多用户同时远程登录
author: 摩摩诘
type: post
date: 2014-08-03T15:22:20+00:00
excerpt: 修改Windows 8.1 远程桌面服务相关的系统文件，破解远程桌面连接数限制，以达到多用户远程登录Windows 8.1的目的。消费级的 Windows 在同一时间只支持一个用户远程登陆，但是有时我们会需要两个甚至更多用户同时操作一台电脑，为实现这个目的，我们可以修改远程桌面服务相关的系统文件，破解远程桌面连接数限制。
url: /articles/windows81-remote-desktop-concurrent-users.html
index_image:
  - https://www.digglife.net/wp-content/uploads/2014/08/windows8-remote-desktop.jpg
views:
  - 6796
duoshuo_thread_id:
  - 1154125469839262184
categories:
  - Windows技巧
tags:
  - windows
  - windows8
  - 远程桌面

---
消费级的 Windows 在同一时间只支持一个用户远程登陆，但是有时我们会需要两个甚至更多用户同时操作一台电脑，为实现这个目的，我们可以修改远程桌面服务相关的系统文件，破解远程桌面连接数限制。

其实对于微软来说，在技术上支持多人同时登录并不是什么问题，只是这样做大概会影响 Windows 的销量，所以即便是多用户使用场景更多的 Server 版 Windows，微软也仅仅开放了两个用户，而且还声明仅限于 System Administration 目的，如果需要更多用户同时使用，合法的手段是额外付费购买Terminal Server License。

<!--more-->

下面是让 **64位 Windows 8.1** 支持多用户同时远程登录的方法。

首先确认 termsrv.dll 的版本号。2014年7月微软发布了一个远程桌面服务相关的补丁，文件版本从 v6.3.9600.16384 更新到了 v6.3.9600.17095，需要修改的 code 不一样。

<img src="https://www.digglife.net/wp-content/uploads/2014/08/termsrv.png" alt="远程桌面服务termsrv.dll" width="452" height="318" class="alignnone size-full wp-image-3825" />

在修改或者替换termsrv.dll 之前，需要先停止远程桌面服务。可以通过 `services.msc` 调出服务控制台，找到 `Remote Desktop Service` 选择停止。也可以直接使用管理员权限执行命令 `net stop termservice`。系统会提示依赖服务RPC同样会被停止，确定。

以下手动修改或者直接替换任选一种。如果你对这里下载的文件没有安全感，推荐第一种。

  1. 手动修改 termsrv.dll 的 Hex
使用一个靠谱的hex编辑器编辑 termsrv.dll 文件。

  * v6.3.9600.17095
`8B 81 38 06 00 00 39 81 3C 06 00 00 0F 84 1B 70 00 00`
  
修改成
  
 `B8 00 01 00 00 89 81 38 06 00 00 90 90 90 90 90 90 90`

  * v6.3.9600.16384
`39 81 3C 06 00 00 0F 84 9E 31 05 00`
  
修改成
  
`B8 00 01 00 00 89 81 38 06 00 00 90` </ul> 

  * 下载已经破解好的 termsrv.dll 文件
  * [破解版 termsrv.dll v6.3.9600.16384 下载][1]
  * [破解版 termsrv.dll v6.3.9600.17095 下载][2]</ol> 

有两点需要说明：

  1. 理论上，修改 Windows 的系统文件是违反最终用户许可协议的。
  2. 如果以后通过 Windows Update 安装了远程桌面服务的相关更新，修改会失效。

其实同样的目的我们也可以安装VNC Server，但是和Windows的远程桌面服务相比，VNC差太远了，几乎不是一个级别的技术。Windows里有很多微软的黑科技，RDP其实都算的上一个。

 [1]: https://www.digglife.net/wp-content/uploads/files/termsrv_6.3.9600.16384.zip "termsrv_6.3.9600.16384.zip"
 [2]: https://www.digglife.net/wp-content/uploads/files/termsrv_6.3.9600.17095.zip "termsrv_6.3.9600.17095.zip"
