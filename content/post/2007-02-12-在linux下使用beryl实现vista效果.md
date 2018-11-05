---
title: ubuntu 6.10 edgy beryl安装日志
author: 摩摩诘
type: post
date: 2007-02-12T04:50:06+00:00
url: /articles/在linux下使用beryl实现vista效果.html
related_posts:
  - 'a:2:{s:4:"time";i:1224886374;s:13:"related_posts";s:1654:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/install-compiz-fusion-and-trouble-shooting-part2-2.html" title="Ubuntu Compiz Fusion安装和常见问题解决 Part.2">Ubuntu Compiz Fusion安装和常见问题解决 Part.2</a></li><li><a href="http://www.digglife.cn/articles/install-compiz-fusion-and-trouble-shooting-part1-2.html" title="Ubuntu Compiz Fusion安装和常见问题解决 Part.1">Ubuntu Compiz Fusion安装和常见问题解决 Part.1</a></li><li><a href="http://www.digglife.cn/articles/how-to-install-kde40-in-ubuntu.html" title="如何在Ubuntu 7.10下安装KDE 4.0">如何在Ubuntu 7.10下安装KDE 4.0</a></li><li><a href="http://www.digglife.cn/articles/ubuntu%e6%9c%80%e7%ae%80%e5%8d%95%e7%9a%84ubuntu%e5%ae%89%e8%a3%85%e5%b7%a5%e5%85%b7wubiwindows-xp.html" title="Ubuntu:最简单的Ubuntu安装工具:Wubi(Windows XP)">Ubuntu:最简单的Ubuntu安装工具:Wubi(Windows XP)</a></li><li><a href="http://www.digglife.cn/articles/ubuntu17%e6%ac%beubuntu%e6%96%b0%e6%89%8b%e5%bf%85%e5%a4%87%e7%9a%84%e8%b6%85%e9%85%b7%e8%bd%af%e4%bb%b6part1.html" title="Ubuntu:17款Ubuntu新手必备的超酷软件(Part.1)">Ubuntu:17款Ubuntu新手必备的超酷软件(Part.1)</a></li><li><a href="http://www.digglife.cn/articles/%e9%85%b7%e8%bd%af%e6%8e%a8%e8%8d%90%e8%ae%a9windows%e4%b9%9f%e7%94%a8%e4%b8%8a3d%e6%a1%8c%e9%9d%a2.html" title="酷软推荐:让windows也用上3D桌面">酷软推荐:让windows也用上3D桌面</a></li><li><a href="http://www.digglife.cn/articles/add-compiz-fusion-stackswitch.html" title="Compiz Fusion新特效Stackswitch">Compiz Fusion新特效Stackswitch</a></li></ul>";}'
views:
  - 1921
bot_views:
  - 1931
duoshuo_thread_id:
  - 1154125469839261702
categories:
  - Ubuntu技巧
tags:
  - beryl
  - Linux
  - ubuntu
  - XGL
  - 主题
  - 美化

---
Beryl是linux平台的一款桌面效果优化软件,他能够极大地改善Linux的桌面体验.其代表性特效有:3D立方体桌面,透明效果,窗口折叠,果冻效果等等.配置beryl也没有什么技术含量,只是需要耐心和细心而已,查找和阅读的时候多留意重点就行了.

> ### **基本流程是:**
> 
>   1. 安装显卡驱动
>   2. 下载安装beryl
>   3. 配置xorg.conf文件
>   4. 重启Xwindow后启动beryl

### **一.显卡驱动安装.(以NVIDIA显卡为例)**

显卡驱动安装有两种方式,一种是在终端输入sudo apt-get install NVIDIA-glx下载安装.这种方法在我的机器上失效,所以不做多的介绍.下面介绍最猛的安装官方驱动的方法.

1.确认版本.要确认你的系统是全新安装的ubuntu6.10,而不是从6.06升级上来的，否则可能会出问题。
  
2.下载驱动.到<http://www.nvidia.com/object/unix.html>下载对应32/64位版本的驱动.

> 下载驱动的时候注意了,如果你的显卡低于Geforce2 MX440(包括Geforce2 MX440),比如TNT等等,你需要下载1.0-96\*\*的驱动,到上面的网站搜索就行了.我第一次就是下的97\*\*,搞得无法安装.

3.前期准备.

删除原有驱动(假设你安装过源里面的nvidia-glx驱动，如果没有装过或曾经手动安装驱动的可以跳过）：
  
_sudo apt-get –purge remove nvidia-glx
  
_ 恢复X的设置
  
sudo cp /etc/X11/xorg.conf.backup /etc/X11/xorg.conf
  
重启，确定起动正常

执行命令：
  
sudo gedit /etc/default/linux-restricted-modules-common
  
在最后的双引号里面添加nv两个字，添加后就是“nv”

预防起动X失败的备份
  
sudo cp /etc/X11/xorg.conf /etc/X11/xorg.conf.mybackup
  
如果起动X失败，可以用sudo cp /etc/X11/xorg.conf.mybackup /etc/X11/xorg.conf来恢复X设置，然后启动.

以下为网络上流传的要点，原贴作者多台机器安装没有使用，我安装的时候也没有用，如果不 行，可以尝试（但是会删除受限制模块，导致某些别的硬件无法使用：
  
sudo apt-get –purge remove nvidia-settings nvidia-kernel-common
  
sudo rm /etc/init.d/nvidia-*

4.开始安装.（对于曾经手动安装nv驱动的，可以在安装的时候选择卸载旧版的驱动）：

<font color="#ff0000">请拿出一张纸和一支笔，记录下一下的命令.</font>因为我们要去到纯终端里面安装.
  
注销后，按Ctrl+Alt+F1，输入用户名和密码，登录后关闭gdm：
  
sudo /etc/init.d/gdm stop
  
然后开始安装（假设下载的文件放在/home/lans/目录下）
  
sudo sh /home/lans/NVIDIA-Linux-x86-1.0-9629-pkg1.run(根据你下载的文件做出更改)

进入安装界面后，首先接受协议，选“接受”
  
可能会有提示已经安装了旧的驱动（视乎你自己是否有手动安装过），是否删除，选yes就是了， 一般会提示缺少模块，问是否网上下载，选“no”，提示需要自己编译模块，选“ok”，然后编译安装开始， 最后提示需要修改xorg.conf，是否允许，选yes，完成安装，选ok。
  
然后回到终端界面,重启gdm:
  
sudo /etc/init.d/gdm start
  
现在可以重启试试驱动是否已经装好，在“应用程序-》系统工具-》NVIDIA X server setting里面可以看到驱动的信息
  
<font color="#800040">提示：每次更新内核后都需要重新安装nv的驱动！</font>

### 二.beryl安装.

1.添加源 ：
  
sudo gedit /etc/apt/sources.list
  
加入以下源的其中一个 ：
  
deb <http://www.beerorkid.com/compiz> edgy main-edgy
  
deb <http://media.blutkind.org/xgl/> edgy main-edgy
  
deb <http://compiz-mirror.lupine.me.uk/> edgy main-edgy
  
deb <http://ubuntu.compiz.net/> edgy main-edgy
  
如果是64位的：
  
deb <http://www.beerorkid.com/compiz> edgy main-edgy main-edgy-amd64
  
deb <http://media.blutkind.org/xgl/> edgy main-edgy main-edgy-amd64
  
deb <http://compiz-mirror.lupine.me.uk/> edgy main-edgy main-edgy-amd64
  
deb <http://ubuntu.compiz.net/> edgy main-edgy main-edgy-amd64
  
保存后退出
  
然后加入钥匙，在控制台输入：（下面的任选其一）
  
wget <http://www.beerorkid.com/compiz/quinn.key.asc> -O &#8211; | sudo apt-key add &#8211;
  
wget <http://media.blutkind.org/xgl/quinn.key.asc> -O &#8211; | sudo apt-key add &#8211;
  
wget <http://compiz-mirror.lupine.me.uk/quinn.key.asc> -O &#8211; | sudo apt-key add &#8211;
  
wget <http://ubuntu.compiz.net/quinn.key.asc> -O &#8211; | sudo apt-key add &#8211;

<font color="#800040">我安装的时候这4个没有一个连得上,后来上英文Wiki找到另外一个才解决的. </font>

sudo echo && wget <http://ubuntu.beryl-project.org/root@lupine.me.uk.gpg>-O- | sudo apt-key add &#8211;

刷新库
  
sudo apt-get update
  
sudo apt-get dist-upgrade
  
2.安装beryl
  
sudo apt-get install beryl emerald emerald-themes

### 三.配置xorg.conf

执行命令:
  
sudo gedit /etc/X11/xorg.conf
  
在 Section “Screen” 里面添加
  
Option “AddARGBGLXVisuals” “True”
  
保存并退出.
  
下面为可选
  
在 Section &#8220;Device&#8221; 里面添加
  
Option &#8220;TripleBuffer&#8221; &#8220;true&#8221;
  
添加如下一项：
  
Section &#8220;Extensions&#8221;
  
Option &#8220;Composite&#8221; &#8220;Enable&#8221;
  
EndSection
  
保存退出
  
最后,在系统-》首选项-》会话-》起动程序 里面添加一项&#8221;beryl-manager&#8221;
  
注销
  
alt+ctrl+backspace，重启X
  
再登录，就可以看到beryl的效果了。
  
**附：错误解决
  
** 如果出现窗口框闪烁，可以在系统-》首选项-》会话-》起动程序 里面添加一项&#8221;emerald –replace&#8221;

**效果展示:(点击放大)**

[![beryleffect1.png][1]][2]

 [![beryleffect2.png][3]][4]

<font color="#ff0000">提示:</font>
  
beryl 除了自己附带的主题，还可以到下面的地址下载更多主题.
  
<http://browse.deviantart.com/customization/skins/linuxutil/>
  
<http://gnome-look.org/>

> 以上内容大部分来自Ubuntu中文论坛Lans兄弟的帖子,在此表示万分感谢.[他的博客][5]
> 
>  Ubuntu中文论坛原帖地址:
> 
> <http://forum.ubuntu.org.cn/viewtopic.php?t=32798&highlight=%E5%9C%86%E4%BD%93>
> 
>  英文wiki安装方法地址:
> 
> [http://wiki.beryl-project.org/wiki/Install\_Beryl\_on_Ubuntu**\_Edgy\_with_nVidia**][6]

 [1]: https://www.digglife.net/wp-content/uploads/3/379/2007/05/beryleffect1.thumbnail.png
 [2]: https://www.digglife.net/wp-content/uploads/3/379/2007/05/beryleffect1.png "beryleffect1.png"
 [3]: https://www.digglife.net/wp-content/uploads/3/379/2007/05/beryleffect2.thumbnail.png
 [4]: https://www.digglife.net/wp-content/uploads/3/379/2007/05/beryleffect2.png "beryleffect2.png"
 [5]: http://cheerin.blogcn.com/
 [6]: http://wiki.beryl-project.org/wiki/Install_Beryl_on_Ubuntu_Edgy_with_nVidia
