---
title: Broadcom BCM 5787的Leopard驱动
author: 摩摩诘
type: post
date: 2008-10-29T04:16:41+00:00
url: /articles/broadcom-bcm5787-driver-leopard.html
index_image:
  - https://www.digglife.net/wp-content/uploads/2008/10/mac-osx-leopard.jpg
views:
  - 5083
bot_views:
  - 2496
syntaxhighlighter_encoded:
  - 1
duoshuo_thread_id:
  - 1154125469839262113
categories:
  - Windows技巧
tags:
  - hackintosh
  - leopard
  - mac
  - 破解
  - 苹果
  - 驱动

---
很久之前我尝试过<a title="PC上安装Mac OSX Leopard" href="https://www.digglife.net/articles/install-leopard-on-pc.html" target="_blank">在笔记本上安装Mac OS X Leopard</a>，可是由于有线和无线网卡都没有驱动，所以只好放弃。前些日子无意中发现InsanelyMac上有强人发布了Broadcom BCM 5787的驱动（搜索了半天没有找到原帖），而且跟帖的朋友纷纷表示能够完美运行，正好我也没有删除Leopard，索性没事所以立马尝试了一把，结果证明这个Kext果然异常强大，能够完美驱动Broadcom BCM 5787这个长期无解困扰了无数人的网卡。安装过程非常傻瓜化，下面做个简单的介绍，权当笔记。

<!--more-->


  
 <span style="color: #ff0000;">注意：本驱动仅仅适合ID号为14e4:1693的Broadcom BCM 5787，其他ID的不保证能够运行。 </span>

### 1.工具和驱动的准备

下载Kext安装工具 <a title="Kext Helper b7下载" href="http://www.rayfile.com/files/fd909a14-a56b-11dd-990e-0014221b798a/" target="_blank">Kext Helper B7</a>和<a title="Broadcom BCM 5787驱动" href="http://www.rayfile.com/files/35d3a54c-a56c-11dd-b086-0014221b798a/" target="_blank">Broadcom BCM 5787驱动</a>。
  
Kext Helper是一个能够自动化Kext安装的工具，让普通用户也能简单地完成驱动安装操作。可能很多玩过Hackintosh的朋友对这个工具都非常了解，我在当时安装的时候才知道有这么个玩意。

### 2.安装

解压缩保存在硬盘的驱动，将名为AppleBCM5787MEthernet.kext的文件拖放到Kext Helper B7的窗口中，输入Leopard的帐户密码，点击Easy Install。如果一切顺利，应该会有一个弹出窗口让你”双手合十并重启“（Cross Your Fingers and Reboot）。

<img class="alignnone" title="Kext Helper B7 初始状态" src="http://digglife.qiniudn.com/wp-content/uploads/archive/Kext%20Helper%200.7.jpg" alt="" width="400" height="209" />
  
重启之后可以点开”系统偏好设置“，查看”网络“，这个时候以太网前面的那个小球应该变绿了，这表示Leopard已经识别出网卡；如果还是红的，表示系统尚未网卡，你可以尝试重新安装驱动。我的情况是第二次安装才成功，而且第二次安装后并没有重启系统即可正常工作。

这是网卡还不是活跃的，所以还是无法联网。

### 3.激活网卡

在终端中输入sudo tcpdump -i enX，其中X是网卡的编号，一般情况下有线网卡都是0。输入帐户密码执行命令后，你可以看到网卡的活动信息，到这里你就可以打开Safari光顾一下Apple的主页了。

<img class="alignnone" title="Mac OS X Leopard有线网卡状态" src="http://digglife.qiniudn.com/wp-content/uploads/archive/Ethernet.jpg" alt="" width="400" height="322" />

### 4.自动激活网卡

压缩包中还有一个文件夹名为Start\_Promisc，这是另外一位国际友人编写的脚本，能够让Leopard启动时就自动激活网卡。首先要将Start\_Promisc文件夹复制到/Library/StartupItems/中，然后用文本编辑器修改start_promisc文件中开头的INF和KEXTPATH为你的网卡编号和驱动路径，下面是我修改后的：

> INTF=&#8221;en0&#8243;
  
> KEXTPATH=&#8221;/System/Library/Extensions/AppleBCM5787MEthernet.kext&#8221;

最后运行下列命令以授权：

>   sudo chmod -R 755 /Library/StartupItems/Start_Promisc
> 
>   sudo chown -R root:wheel /Library/StartupItems/Start_Promisc

完成后重启，相比重启后你就能够直接上网而不用输入麻烦的命令了。

这个驱动非常完美，我断断续续用了这么长时间，没有出现过一次问题。安装了这个驱动之后才发现，其实在Leopard下风扇转的很厉害，所以重装了一下，在自定义安装中勾了几个之前没有选择的东西，现在非常舒服，不过还是存在一些问题，比如触摸板无法禁用，前置音频接口无法使用，无线网卡无法驱动等，不过也无所谓了，反正也只是玩玩而已，没有想过在Leopard下做什么事情。