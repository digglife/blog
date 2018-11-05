---
title: 老迈的 Macbook Pro 也有了Fusion Drive
author: 摩摩诘
type: post
date: 2014-02-02T00:09:18+00:00
excerpt: 前天给老迈的MacBook Pro加装了一块固态硬盘（ SDD ），和原装的机械硬盘（ HDD ）组装成了Fusion Drive，算是给 MBP 也过了个年。因为以前也拆过 MBP 的光驱，所以拆解过程都非常顺利。软件部分因为事前准备比较充分，加上创建 Fusion Drive 的原理几乎和 LVM 一样，所以也没遇到什么问题。
url: /articles/macbook-pro-2010-fusion-drive.html
index_image:
  - https://www.digglife.net/wp-content/uploads/2014/02/Fusion-Drive-logo-Apple.jpg
duoshuo_thread_id:
  - 1154125469839262169
views:
  - 834
categories:
  - Mac学习
tags:
  - mac
  - OSX
  - sdd

---
前天给[老迈的MacBook Pro][1]加装了一块固态硬盘（ SDD ），和原装的机械硬盘（ HDD ）组装成了<a title="Fusion Drive" href="http://zh.wikipedia.org/wiki/Fusion_Drive" target="_blank">Fusion Drive</a>，算是给 MBP 也过了个年。以前为了清洗光头也拆过 MBP 的光驱，所以拆解过程都非常顺利。软件部分因为事前准备比较充分，加上创建 Fusion Drive 的原理几乎和 LVM 一样，所以也没遇到什么问题。

之前有不少人表示只有台式Mac（ iMac 和 Mac Mini ）才能创建真正的Fusion Drive，质疑给 MacBook 手动创建 Fusion Drive 的实际效果，但是就我实际使用的体验来看还是不错的。另外，<a title="imvenj facebook" href="https://www.facebook.com/im.venj" target="_blank">@imvenj </a>提到有传言说Fusion Drive不支持 <a title="Trim command " href="http://en.wikipedia.org/wiki/TRIM_%28SSD_command%29" target="_blank">SDD 的 TRIM </a>功能，但暂时未得到证实。

大体做一下笔记。

### 准备部分

  1. Time Machine完整备份
  2. Mavericks启动U盘

因为利用 <a title="Mac OS X Lion Adds CoreStorage, a Volume Manager" href="http://blog.fosketts.net/2011/08/04/mac-osx-lion-corestorage-volume-manager/" target="_blank">CoreStorage</a> 重新组织磁盘系统必然会抹掉现有HDD上的所有数据，所以需要全盘备份和启动U盘。OS X体积逐年膨胀，单层 DVD 已经容不下了，苹果也意识到了这一点，于是在 Mavericks 的安装APP里放了一个 creatinstallmedia 的CLI程序，可以直接拿来创建可启动的安装磁盘。（印象中Mountain Lion还没有这个）

`createinstallmedia --volume #path to volume to convert# --applicationpath #path to Install OS X Mavericks.app# [--force]`

### 硬件更换

我买的是 <a title="Kingston SDD V300 120GB" href="http://click.union.jd.com/JdClick/?unionId=1888&t=4&to=http://www.jd.com/product/779351.html" target="_blank">Kingston V300 120GB</a>，只有一个原因，便宜。此外，即便买芯片更好速度更快的 SanDisk 至尊极速之流，受限于主板只支持 <a title="SATA revision 2.0 - 3 Gbit/s - 300 MB/s" href="http://en.wikipedia.org/wiki/Serial_ATA#SATA_revision_2.0_-_3_Gbit.2Fs_-_300_MB.2Fs" target="_blank">SATA2</a>，高于 300Gbps 的磁盘读写速度都无法在我这台 MBP 上体现出来，买了也是白买，所以够用就好了。

为了把 SDD 放在以前的光驱位，我还买了个便宜的 <a title="笔记本光驱位硬盘托架（9.5mm通用型）" href="http://click.union.jd.com/JdClick/?unionId=1888&t=4&to=http://www.jd.com/product/620931.html" target="_blank">9.5mm 通用光驱位硬盘架</a>。原装的三菱吸入式光驱周围有三个用于固定的螺丝位，这种通用的架子没有，好在原装光驱上有一个可以取下来加装在架子上，加上压在光驱上的喇叭可以固定得很紧，所以基本上没有什么问题。不过还是**建议购买MBP专用的光驱位硬盘架**，省去很多麻烦。

### 创建Fusion Drive

Fusion Drive创建的原理和 LVM 基本类似，同样也是PV->VG->LV的模式。Fusion Drive不过是VG里面有SSD，而且在实际工作中可以根据用户的使用频率自动调整文件在PV中的存放位置而已。

  1. 开机后按住Option，进入启动菜单，选择事前创建的启动U盘。启动后进入{终端}。
  2. 列出已连接的物理磁盘
`diskutil list`

  3. 创建 Fusion Drive ( CoreStorage VG )
详细语法可以输入 `diskutil cs create` 查看。

`diskutil cs create Fusion disk0 disk1`

<img src="https://www.digglife.net/wp-content/uploads/2014/02/osx-create-fusion-drive.jpg" alt="创建Fusion Drive命令" width="500" height="281" class="alignnone size-full wp-image-3741" />

创建出来的磁盘UUID会在下面的命令中用到。

  4. 创建逻辑磁盘
`diskutil cs createVolume BB7BC34F-64A1-4BB9-BAE3-39402CE34867 jhfs+ Mac 100%`

  5. 完成

然后重新安装Mavericks 或者 从 Time Machine 备份恢复就OK了。

因为OS和Application都自动放在了SDD，所以无论是系统还是应用的启动和运行速度都有了质的提高，这种感觉好久不曾有。

 [1]: https://www.digglife.net/devices "Macbook Pro MId 2010 "
