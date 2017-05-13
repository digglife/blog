---
title: 利用VMware在Ubuntu下使用已有的Windows软件.
author: 摩摩诘
type: post
date: 2007-07-21T04:19:52+00:00
url: /articles/run-every-windows-app-on-ubuntu.html
0:
  - 547c97dfe78415cdc11783a454162568a902f6534e194fda987d2504e927df48f6369b8945b291cabf47a76bea4f77a8
  - 547c97dfe78415cdc11783a454162568a902f6534e194fda987d2504e927df48f6369b8945b291cabf47a76bea4f77a8
1:
  - 64166e164f623e2e576ed13f58029d29e5957efdfc8a84bb36c43211ad87c35e7050451af117ed2c48f735bf7f061bc7
  - 64166e164f623e2e576ed13f58029d29e5957efdfc8a84bb36c43211ad87c35e7050451af117ed2c48f735bf7f061bc7
2:
  - f2c6be7c9223086c8aa6c6f4a14d4db1409611e44e9a4eec2653b99865e80711320d79eec7a72c4d57b29059a230c93f
  - f2c6be7c9223086c8aa6c6f4a14d4db1409611e44e9a4eec2653b99865e80711320d79eec7a72c4d57b29059a230c93f
3:
  - 4730e299f409e5edc462dd119ca7654331b47e8dc3b1979a4f39ec1c03b686751908107441c0657b50a28f1dee9d604c
  - 4730e299f409e5edc462dd119ca7654331b47e8dc3b1979a4f39ec1c03b686751908107441c0657b50a28f1dee9d604c
4:
  - 57a48ed002087b4483a5e83d8b5877af41a53fe18bbb8416acc4337b48879af57b45ad2bf9b0f0361a7751bfd50d4eb4
  - 57a48ed002087b4483a5e83d8b5877af41a53fe18bbb8416acc4337b48879af57b45ad2bf9b0f0361a7751bfd50d4eb4
comment_count:
  - 4
related_posts:
  - 'a:2:{s:4:"time";i:1224885964;s:13:"related_posts";s:1543:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/ubuntu%e6%9c%80%e7%ae%80%e5%8d%95%e7%9a%84ubuntu%e5%ae%89%e8%a3%85%e5%b7%a5%e5%85%b7wubiwindows-xp.html" title="Ubuntu:最简单的Ubuntu安装工具:Wubi(Windows XP)">Ubuntu:最简单的Ubuntu安装工具:Wubi(Windows XP)</a></li><li><a href="http://www.digglife.cn/articles/how-to-install-kde40-in-ubuntu.html" title="如何在Ubuntu 7.10下安装KDE 4.0">如何在Ubuntu 7.10下安装KDE 4.0</a></li><li><a href="http://www.digglife.cn/articles/install-compiz-fusion-and-trouble-shooting-part2-2.html" title="Ubuntu Compiz Fusion安装和常见问题解决 Part.2">Ubuntu Compiz Fusion安装和常见问题解决 Part.2</a></li><li><a href="http://www.digglife.cn/articles/install-compiz-fusion-and-trouble-shooting-part1-2.html" title="Ubuntu Compiz Fusion安装和常见问题解决 Part.1">Ubuntu Compiz Fusion安装和常见问题解决 Part.1</a></li><li><a href="http://www.digglife.cn/articles/ubuntu-emagazine-full-circle-4.html" title="Ubuntu电子杂志《Full Circle》第4期上线">Ubuntu电子杂志《Full Circle》第4期上线</a></li><li><a href="http://www.digglife.cn/articles/ubuntu-emagazine-full-circle-3.html" title="Ubuntu电子杂志《Full Circle》第3期上线">Ubuntu电子杂志《Full Circle》第3期上线</a></li><li><a href="http://www.digglife.cn/articles/ubuntu-emagazine-full-circle-2.html" title="Ubuntu电子杂志《Full Circle》第2期上线">Ubuntu电子杂志《Full Circle》第2期上线</a></li></ul>";}'
views:
  - 7192
bot_views:
  - 2222
duoshuo_thread_id:
  - 1154125469839261853
categories:
  - Ubuntu技巧
tags:
  - ubuntu
  - vmware
  - 安装
  - 虚拟机

---
尽管我们有很多人希望常驻<a target="_blank" href="https://www.digglife.net/articles/category/about_ubuntu/">Ubuntu</a>,但是很多时候还是脱离不了<a target="_blank" href="https://www.digglife.net/articles/category/windows-tricks/">Windows</a>.这个时候通常的选择是使用Wine模拟运行Windows软件,但是配置难免复杂,而且很多软件也并不能正常使用.下面这个向导详细说明了如何利用VMware在Ubuntu下运行已经在Windows下安装了的软件,操作很简单.

### **Windows XP下:**

1.首先为VMware制作一个硬件配置文件(为了不影响原配置文件):

  * 点击**开始&#8211;控制面板&#8211;系统**
  * 在**硬件**一栏选择**硬件配置文件**.
  * 点击复制,并将新的配置文件命名为VMware.

<a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/07/hardware-profiles.png"><img width="387" src="http://digglife.qiniudn.com/wp-content/uploads/3/379/2007/07/hardware-profiles-thumb.png" alt="Hardware_profiles" height="383" /></a>

<!--more-->

2.然后安装在VMware中启动Windows必需的SCSI驱动:

  * 下载[VMware SCSI drivers][1]和[WinImage][2]两个文件.
  * 安装并运行Winimage. 在Winimage中打开下载的VMware SCSI驱动并解压至任意目录.
  * 点击开始&#8211;控制面板&#8211;添加新硬件,依照下面的步骤进行 
  *   * 在向导中选择&#8221;**是,我已连接此硬件&#8221;**选项,点击下一步.
      * 你会看到一个硬件列表. 直接拖拽滚动条到最下方,选择&#8221;**添加新的硬件设备**&#8220;.然后下一步.
      * 选择&#8221;**安装我手动从列表中选择的硬件**&#8220;.
      * 选择**SCSI and RAID控制器**. 点击浏览,定位到你刚才解压的VMware SCSI驱动.Windows会自动安装.

<a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/07/scsi.png"><img width="450" src="http://digglife.qiniudn.com/wp-content/uploads/3/379/2007/07/scsi-thumb.png" alt="SCSI" height="350" /></a>

### **重启到Ubuntu**

如果你已经在Ubuntu下挂载了Windows 分区,现在需要卸载它们.

  1. 打开终端,输入**sudo gedit /etc/group** 在以**disk**开头一行的最后加上你的Ubuntu用户名.这一步是为了让VMware获得接入硬盘的权限.
  2. 定位到 **应用程序&#8211;添加删除&#8230;** .搜索并安装**vmware-sever**软件包.这个软件包在国内的源里面似乎都没有,所以如果你不想添加国外源后安装的话,可以直接下载<a target="_blank" href="http://archive.canonical.com/ubuntu/pool/main/v/vmware-server/vmware-server_1.0.3-1_i386.deb">vmware-sever的.deb安装包</a>.当然,我们还可以自己到官方网站上<a target="_blank" href="http://www.vmware.com/download/server/">下载源码包</a>自己编译安装,不过比较复杂,有兴趣的可以看看下面两篇文章.<a target="_blank" href="http://www.howtoforge.com/ubuntu_feisty_fawn_vmware_server_howto" title="http://www.howtoforge.com/ubuntu_feisty_fawn_vmware_server_howto">How to install VMware on Ubuntu 7.04 Feisty Fawn</a> 
    [][3][在Ubuntu 7.04 Feisty Fawn上安装VMware Server][4]</li> 
    
      * 安装最后会提示输入序列号,可以到vmware官网上<a target="_blank" href="http://register.vmware.com/content/registration.html">免费申请</a>.下面是我申请的一些序列号,只用过第一个.
  
        > 9348N-YDV4P-2GM7P-4L634
        > 
        > 99JA5-YDA6K-2GME6-4TQA8
        > 
        > 93M20-Y4G6P-2EN73-4JJJM
        > 
        > 99500-YDZ62-27J52-4T6U5
        > 
        > 93M84-Y6GD2-2GJGP-4V5JX
        > 
        > 93M0J-YFUFK-254G7-4TLJ0
        > 
        > 9902H-Y4FDK-25JGQ-4V4UW
        > 
        > 9140M-YDZF6-27JE7-4VLHW
        > 
        > 9C584-Y4V66-2G4E7-4VPAH
        > 
        > 93401-Y6A4P-2EMGQ-4TQ3W
    
      * `<font face="Trebuchet MS">下面开始配置虚拟机.<br />
定位到 <strong>应用程序--系统工具--VMware Server Console</strong>.选择连接到<strong>本地主机</strong>( local host).下面按照以下步骤进行:</font>`</p> 
          * `<font face="Trebuchet MS">创建一个<strong>自定义虚拟机</strong>(Creat a custom virtual machine)</font>`
        
        <a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/07/custom.png"><img width="450" src="http://digglife.qiniudn.com/wp-content/uploads/3/379/2007/07/custom-thumb.png" alt="custom" height="352" /></a>
        
          * ```<font face="Trebuchet MS">选择你正在使用的Windows版本,一直保持默认设置点击下一步直到网络选项.在这里选择<strong>NAT Networking</strong>.设定<strong>Buslogic</strong>为SCSI控制器(SCSI Controller)</font>`
        
        <a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/07/networking.png"><img width="450" src="http://digglife.qiniudn.com/wp-content/uploads/3/379/2007/07/networking-thumb.png" alt="networking" height="352" /></a>
        
          * `<font face="Trebuchet MS">在<strong>选择磁盘</strong>(Select a Disk)对话框中,选择使用<strong>物理磁盘</strong>(Use a  physical Disk).然后使用个别分区,勾选Windows所在分区和Linux所在分区(因为Grub启动器的部分在Linux分区下).注意别误选了Swap分区.</font>`
      * ``尽管我们有很多人希望常驻<a target="_blank" href="https://www.digglife.net/articles/category/about_ubuntu/">Ubuntu</a>,但是很多时候还是脱离不了<a target="_blank" href="https://www.digglife.net/articles/category/windows-tricks/">Windows</a>.这个时候通常的选择是使用Wine模拟运行Windows软件,但是配置难免复杂,而且很多软件也并不能正常使用.下面这个向导详细说明了如何利用VMware在Ubuntu下运行已经在Windows下安装了的软件,操作很简单.

### **Windows XP下:**

1.首先为VMware制作一个硬件配置文件(为了不影响原配置文件):

  * 点击**开始&#8211;控制面板&#8211;系统**
  * 在**硬件**一栏选择**硬件配置文件**.
  * 点击复制,并将新的配置文件命名为VMware.

<a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/07/hardware-profiles.png"><img width="387" src="http://digglife.qiniudn.com/wp-content/uploads/3/379/2007/07/hardware-profiles-thumb.png" alt="Hardware_profiles" height="383" /></a>

<!--more-->

2.然后安装在VMware中启动Windows必需的SCSI驱动:

  * 下载[VMware SCSI drivers][1]和[WinImage][2]两个文件.
  * 安装并运行Winimage. 在Winimage中打开下载的VMware SCSI驱动并解压至任意目录.
  * 点击开始&#8211;控制面板&#8211;添加新硬件,依照下面的步骤进行 
  *   * 在向导中选择&#8221;**是,我已连接此硬件&#8221;**选项,点击下一步.
      * 你会看到一个硬件列表. 直接拖拽滚动条到最下方,选择&#8221;**添加新的硬件设备**&#8220;.然后下一步.
      * 选择&#8221;**安装我手动从列表中选择的硬件**&#8220;.
      * 选择**SCSI and RAID控制器**. 点击浏览,定位到你刚才解压的VMware SCSI驱动.Windows会自动安装.

<a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/07/scsi.png"><img width="450" src="http://digglife.qiniudn.com/wp-content/uploads/3/379/2007/07/scsi-thumb.png" alt="SCSI" height="350" /></a>

### **重启到Ubuntu**

如果你已经在Ubuntu下挂载了Windows 分区,现在需要卸载它们.

  1. 打开终端,输入**sudo gedit /etc/group** 在以**disk**开头一行的最后加上你的Ubuntu用户名.这一步是为了让VMware获得接入硬盘的权限.
  2. 定位到 **应用程序&#8211;添加删除&#8230;** .搜索并安装**vmware-sever**软件包.这个软件包在国内的源里面似乎都没有,所以如果你不想添加国外源后安装的话,可以直接下载<a target="_blank" href="http://archive.canonical.com/ubuntu/pool/main/v/vmware-server/vmware-server_1.0.3-1_i386.deb">vmware-sever的.deb安装包</a>.当然,我们还可以自己到官方网站上<a target="_blank" href="http://www.vmware.com/download/server/">下载源码包</a>自己编译安装,不过比较复杂,有兴趣的可以看看下面两篇文章.<a target="_blank" href="http://www.howtoforge.com/ubuntu_feisty_fawn_vmware_server_howto" title="http://www.howtoforge.com/ubuntu_feisty_fawn_vmware_server_howto">How to install VMware on Ubuntu 7.04 Feisty Fawn</a> 
    [][3][在Ubuntu 7.04 Feisty Fawn上安装VMware Server][4]</li> 
    
      * 安装最后会提示输入序列号,可以到vmware官网上<a target="_blank" href="http://register.vmware.com/content/registration.html">免费申请</a>.下面是我申请的一些序列号,只用过第一个.
  
        > 9348N-YDV4P-2GM7P-4L634
        > 
        > 99JA5-YDA6K-2GME6-4TQA8
        > 
        > 93M20-Y4G6P-2EN73-4JJJM
        > 
        > 99500-YDZ62-27J52-4T6U5
        > 
        > 93M84-Y6GD2-2GJGP-4V5JX
        > 
        > 93M0J-YFUFK-254G7-4TLJ0
        > 
        > 9902H-Y4FDK-25JGQ-4V4UW
        > 
        > 9140M-YDZF6-27JE7-4VLHW
        > 
        > 9C584-Y4V66-2G4E7-4VPAH
        > 
        > 93401-Y6A4P-2EMGQ-4TQ3W
    
      * `<font face="Trebuchet MS">下面开始配置虚拟机.<br />
定位到 <strong>应用程序--系统工具--VMware Server Console</strong>.选择连接到<strong>本地主机</strong>( local host).下面按照以下步骤进行:</font>`</p> 
          * `<font face="Trebuchet MS">创建一个<strong>自定义虚拟机</strong>(Creat a custom virtual machine)</font>`
        
        <a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/07/custom.png"><img width="450" src="http://digglife.qiniudn.com/wp-content/uploads/3/379/2007/07/custom-thumb.png" alt="custom" height="352" /></a>
        
          * ```<font face="Trebuchet MS">选择你正在使用的Windows版本,一直保持默认设置点击下一步直到网络选项.在这里选择<strong>NAT Networking</strong>.设定<strong>Buslogic</strong>为SCSI控制器(SCSI Controller)</font>`
        
        <a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/07/networking.png"><img width="450" src="http://digglife.qiniudn.com/wp-content/uploads/3/379/2007/07/networking-thumb.png" alt="networking" height="352" /></a>
        
          * `<font face="Trebuchet MS">在<strong>选择磁盘</strong>(Select a Disk)对话框中,选择使用<strong>物理磁盘</strong>(Use a  physical Disk).然后使用个别分区,勾选Windows所在分区和Linux所在分区(因为Grub启动器的部分在Linux分区下).注意别误选了Swap分区.</font>`
      *`` 
      * ```<font face="Trebuchet MS">现在可以启动VM,在Grub菜单中选择Windows.进入后会出现硬件配置菜单选项,选择我们保存的VMware.</font>`
      * `<font face="Trebuchet MS">注意:不要在VM中启动Linux,否则可能会造成文件丢失.</font>`</ol> 
    
    ``
    
    `<font face="Trebuchet MS">OK,如果没有差错的话,你应该能够在虚拟机中看到熟悉的Windows画面了.第一次启动的时候系统会提示安装新硬件,全部选择取消,点击<strong>VM--安装VMware工具</strong>(Install VMware Tools),安装后重启VM就可以了.</font>`
    
    `<font face="Trebuchet MS">如果你的配置还可以的话,运行起来应该还算流畅的.</font>`
    
    `<a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/07/windowsxp-ubuntu.png"><img width="450" src="http://digglife.qiniudn.com/wp-content/uploads/3/379/2007/07/windowsxp-ubuntu-thumb.png" alt="windowsXP_Ubuntu" height="324" /></a> `
    
    ``
    
    `改写自:<a href="http://www.venturecake.com/10-minutes-to-run-every-windows-app-seamlessly-on-your-ubuntu-desktop/" title="http://www.venturecake.com/10-minutes-to-run-every-windows-app-seamlessly-on-your-ubuntu-desktop/"></a><a href="http://www.venturecake.com/10-minutes-to-run-every-windows-app-seamlessly-on-your-ubuntu-desktop/">10 minutes to run every Windows app on your Ubuntu desktop</a>`

 [1]: http://download3.vmware.com/software/vmscsi-1.2.0.4.flp
 [2]: http://america.winimage.com/download/winima80.exe
 [3]: http://linuxdesktop.cn/2007/05/03/how-to-install-vmware-server-on-ubuntu-704-feisty-fawn "http://linuxdesktop.cn/2007/05/03/how-to-install-vmware-server-on-ubuntu-704-feisty-fawn"
 [4]: http://linuxdesktop.cn/2007/05/03/how-to-install-vmware-server-on-ubuntu-704-feisty-fawn