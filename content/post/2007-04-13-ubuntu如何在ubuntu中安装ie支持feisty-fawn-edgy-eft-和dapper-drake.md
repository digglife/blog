---
title: Ubuntu:如何在Ubuntu中安装IE(支持Feisty Fawn, Edgy Eft 和Dapper Drake)
author: 摩摩诘
type: post
date: 2007-04-13T07:59:35+00:00
url: /articles/ubuntu如何在ubuntu中安装ie支持feisty-fawn-edgy-eft-和dapper-drake.html
0:
  - 2e078e0fb5144d40b239901728547820767f0cfa638b102dd311e1121a3f076800acfc60f62489c8630c0f3d83efe246
  - 2e078e0fb5144d40b239901728547820767f0cfa638b102dd311e1121a3f076800acfc60f62489c8630c0f3d83efe246
comment_count:
  - 2
related_posts:
  - 'a:2:{s:4:"time";i:1224863923;s:13:"related_posts";s:1486:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/clean-up-desktop-improve-productivity-2.html" title="彻底清空桌面,让启动程序更加高效Part.2">彻底清空桌面,让启动程序更加高效Part.2</a></li><li><a href="http://www.digglife.cn/articles/clean-up-desktop-improve-productivity-1.html" title="彻底清空桌面,让启动程序更加高效Part.1">彻底清空桌面,让启动程序更加高效Part.1</a></li><li><a href="http://www.digglife.cn/articles/copy-and-paste-with-middle-click.html" title="使用鼠标中键快速进行复制粘贴">使用鼠标中键快速进行复制粘贴</a></li><li><a href="http://www.digglife.cn/articles/recordmydesktop.html" title="Linux平台屏幕录像工具RecordMyDesktop">Linux平台屏幕录像工具RecordMyDesktop</a></li><li><a href="http://www.digglife.cn/articles/skype-for-linux-14-beta-released.html" title="Skype For Linux 1.4 beta发布.">Skype For Linux 1.4 beta发布.</a></li><li><a href="http://www.digglife.cn/articles/how-to-install-software-in-ubuntu.html" title="Ubuntu技巧:Ubuntu软件安装方法完全指南">Ubuntu技巧:Ubuntu软件安装方法完全指南</a></li><li><a href="http://www.digglife.cn/articles/ubuntu17%e6%ac%beubuntu%e6%96%b0%e6%89%8b%e5%bf%85%e5%a4%87%e7%9a%84%e8%b6%85%e9%85%b7%e8%bd%af%e4%bb%b6part2.html" title="Ubuntu:17款Ubuntu新手必备的超酷软件(Part.2)">Ubuntu:17款Ubuntu新手必备的超酷软件(Part.2)</a></li></ul>";}'
views:
  - 3076
bot_views:
  - 1960
duoshuo_thread_id:
  - 1154125469839261722
categories:
  - Ubuntu技巧
tags:
  - ubuntu
  - 软件

---
相信有很多转到Ubuntu平台的人,比如网页设计师,有时候还是需要在IE中测试网页的运作情况.而且,目前有很多网页只能在IE中才能正常显示(主要是一些不符合设计规范的网页).那么在Ubuntu中安装IE就变得非常有必要了.

下面就介绍一下完整的安装过程(只需要你对Ubuntu有基础的了解):

&nbsp;

&nbsp;

### **1.前期准备工作.**

<a href="http://javabeta.yo2.cn/wp-content/uploads/3/379/2007/04/WindowsLiveWriter/UbuntuUbuntuIEFeistyFawnEdgyEftDapperDra_DBA0/logo-ie%5B3%5D.jpg" atomicselection="true"><img style="border-top-width: 0px; border-left-width: 0px; border-bottom-width: 0px; border-right-width: 0px" height="96" src="http://digglife.qiniudn.com/qiniu/36/image/d5524a0d670789e487ad0c32d6077823.jpg" width="100" border="0" /></a> 

网上有一个叫做[IEs4Linux][1] 的安装包提供了一个安装多个版本IE到Linux桌面的简单方法.在安装之前,你必须阅读[这个页面][2]中的协议.Es4Linux是一个开源软件,但是IE不是.如果你想在Linux平台下安装IE,你必须有一个合法的Windows许可证.否则,安装IE就是违法的.(这个在目前的中国基本不用担心).同时,你还要接受Adobe Flash [EULA][3]以便IEs4Linux安装Adobe Flash. 

确认你以普通用户登陆Linux桌面(不能是Root用户),打开一个终端并在里面输入下面介绍的命令. 

&nbsp; 

&nbsp; 

### **2.修改源地址(/etc/apt/sources.list).**

  * 如果你的Ubuntu是**Feisty Fawn**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 在终端中输入:

> sudo&nbsp;gedit /etc/apt/sources.list&nbsp;
> 
> &nbsp;
> 
> 在弹出的文本中加入以下两行:
> 
> &nbsp;
> 
> deb http://de.archive.ubuntu.com/ubuntu feisty universe 
> 
> deb http://wine.budgetdedicated.com/apt edgy main

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 保存后运行:

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; sudo apt-get update

&nbsp;

  * 如果你的Ubuntu是**Edgy Eft**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 在终端中输入:

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;sudo&nbsp;gedit /etc/apt/sources.list&nbsp;

&nbsp;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 在弹出文本中加入以下两行:

&nbsp;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; deb http://de.archive.ubuntu.com/ubuntu edgy universe 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; deb http://wine.budgetdedicated.com/apt edgy main

&nbsp;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 保存后运行:

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; sudo apt-get update

&nbsp;

  * 如果你的Ubuntu是**Dapper Drake**

&nbsp;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 在终端中输入:

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;sudo&nbsp;gedit /etc/apt/sources.list&nbsp;

&nbsp;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 在弹出文本中加入以下两行:

&nbsp;</p> 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; deb http://de.archive.ubuntu.com/ubuntu dapper universe 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; deb http://wine.budgetdedicated.com/apt dapper main

&nbsp;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 保存后运行:

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; sudo apt-get update

# &nbsp;

### **3.安装wine和cabextract**

在终端中输入:

sudo apt-get install wine cabextract

如果有提示是否安装未加验证的安装包,回答Y.

### &nbsp;

### **4.安装IEs4Linux**

安装IEs4Linux需要执行一下命令

> cd ~   
> wget http://www.tatanka.com.br/ies4linux/downloads/ies4linux-latest.tar.gz  
> tar zxvf ies4linux-latest.tar.gz  
> cd ies4linux-*  
> ./ies4linux

所有的提示都回答Y

&nbsp;

### **5.测试运行**

关闭终端,在桌面上可以看到图片所示图标:

<a href="http://javabeta.yo2.cn/wp-content/uploads/3/379/2007/04/WindowsLiveWriter/UbuntuUbuntuIEFeistyFawnEdgyEftDapperDra_DBA0/1%5B9%5D.jpg" atomicselection="true"><img style="border-top-width: 0px; border-left-width: 0px; border-bottom-width: 0px; border-right-width: 0px" height="379" src="http://digglife.qiniudn.com/qiniu/36/image/24be6cfef10fca8f4ff4eadcb6f295e7.jpg" width="381" border="0" /></a> 

&nbsp;

&nbsp;分别打开6.0,5.5和5.0并在帮助菜单中选择关于,你会看到:

<a href="http://javabeta.yo2.cn/wp-content/uploads/3/379/2007/04/WindowsLiveWriter/UbuntuUbuntuIEFeistyFawnEdgyEftDapperDra_DBA0/3%5B7%5D.png" atomicselection="true"><img style="border-top-width: 0px; border-left-width: 0px; border-bottom-width: 0px; border-right-width: 0px" height="410" src="http://digglife.qiniudn.com/qiniu/36/image/3b1383f3e47036b9a89f469841e03f96.png" width="453" border="0" /></a> 

<a href="http://javabeta.yo2.cn/wp-content/uploads/3/379/2007/04/WindowsLiveWriter/UbuntuUbuntuIEFeistyFawnEdgyEftDapperDra_DBA0/4%5B9%5D.png" atomicselection="true"><img style="border-top-width: 0px; border-left-width: 0px; border-bottom-width: 0px; border-right-width: 0px" height="410" src="http://digglife.qiniudn.com/qiniu/36/image/2cd1cfd373241977a48a699fad0d45ef.png" width="453" border="0" /></a> 

<a href="http://javabeta.yo2.cn/wp-content/uploads/3/379/2007/04/WindowsLiveWriter/UbuntuUbuntuIEFeistyFawnEdgyEftDapperDra_DBA0/5%5B9%5D.png" atomicselection="true"><img style="border-top-width: 0px; border-left-width: 0px; border-bottom-width: 0px; border-right-width: 0px" height="410" src="http://digglife.qiniudn.com/qiniu/36/image/b035e0dfd8bbd3c1b65944977d9df0e6.png" width="453" border="0" /></a>

 [1]: http://www.tatanka.com.br/ies4linux/page/Main_Page
 [2]: http://www.tatanka.com.br/ies4linux/page/Legal_notices
 [3]: http://www.adobe.com/products/eulas/players/flash/