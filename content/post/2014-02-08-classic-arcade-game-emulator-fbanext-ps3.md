---
title: PS3用街机（CPS/NEOGEO）模拟器FBAnext
author: 摩摩诘
type: post
date: 2014-02-07T16:44:41+00:00
excerpt: PS3用街机（CPS/NEOGEO）模拟器FBAnext的使用和经典街机游戏ROM下载。在PS3上借助于FBAnext的移植版，我们可以使用PS3的Dual Shock手柄来体会到接近于当年街机摇杆操作的体验，而且画面上看起来都是 1080P@60fps ，比街机的更带感 。
url: /articles/classic-arcade-game-emulator-fbanext-ps3.html
index_image:
  - https://www.digglife.net/wp-content/uploads/2014/02/ps3-fbanext.jpg
duoshuo_thread_id:
  - 1154125469839262176
views:
  - 3079
wp-syntax-cache-content:
  - |
    a:1:{i:1;s:1393:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="xml" style="font-family:monospace;"><span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;path<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>/dev_hdd0/game/ROMS00000/FBA/<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/path<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>
    <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;path<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>/dev_usb001/FBANext-ROMS/<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/path<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>
    <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;path<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>/dev_usb001/ROMS/<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/path<span style="color: #000000; font-weight: bold;">&gt;</span></span></span></pre></td></tr></table><p class="theCode" style="display:none;">&lt;path&gt;/dev_hdd0/game/ROMS00000/FBA/&lt;/path&gt;
    &lt;path&gt;/dev_usb001/FBANext-ROMS/&lt;/path&gt;
    &lt;path&gt;/dev_usb001/ROMS/&lt;/path&gt;</p></div>
    ";}
categories:
  - 数位游戏
tags:
  - cps
  - neogeo
  - ps3
  - 街机

---
和主机游戏相比，经典街机游戏（以大名鼎鼎的 <a href="http://en.wikipedia.org/wiki/CP_System" title="卡普空 CPS街机" target="_blank">CPS </a>和 <a href="http://en.wikipedia.org/wiki/Neogeo" title="NEOGEO街机" target="_blank">NEOGEO</a> 为最）有着不可取代的魅力，特别是对于八零九零后来说更是童年美好记忆的一部分。Google Play市场上各种经过简单封装的街机App都能在不时在排行榜上占据比较靠前的位置，经典街机的吸引力可见一斑。但是无论是键盘还是触摸屏都无法和当年的摇杆相提并论，更难以体会到多人合作闯关或者格斗对战的快感。在PS3上借助于<a href="http://www.pshomebrew.net/wiki/FBAnext" title="PS3 FBAnext Wiki" target="_blank">FBAnext</a>的移植版，我们可以使用Dual Shock手柄来体会到接近于当年摇杆操作的体验，而且画面上看起来都是 1080P@60fps ，比街机的更带感 。

<!--more-->

[官方的 XMB][1] 是一个完全封闭的系统，所以要安装FBAnext，前提是**PS3上已经是自制系统（CFW）**。特别要提到的是，安装自制系统并不意味着玩盗版，只是能够可以获取对PS3的完全控制权，安装未经 SONY 认证的第三方软件，在这个意义上和 iPhone 的 Jailbreak 是一样的。我的PS3上安装的是[Rebug][2] CFW 4.3，因此以下所有内容都以此为前提。

<img src="http://digglife.qiniudn.com/wp-content/uploads/2014/02/ps3-fbanext-game-menu-500x281.jpg" alt="PS3街机模拟器FBAnext的图标" width="500" height="281" class="alignnone size-medium wp-image-3752" />

### 安装FBAnext For PS3

  1. 下载FBAnext
PS3Homebrew 上似乎已经不提供 FBAnext 的下载，我上传了一份到百度盘=> <a href="http://pan.baidu.com/s/1qWjQRGK" title="PS3用街机模拟器FBAnext百度盘下载" target="_blank">PS3用街机模拟器FBAnext百度盘下载</a>

  2. 复制压缩包内的文件到任意USB存储设备根目录，或使用 FTP 上传
<a href="http://psx-scene.com/forums/f192/multiman-multifunctional-tool-your-ps3-game-manager-file-manager-ftp-avchd-bdmv-72826/" title="PS3多功能游戏及文件管理软件Multiman" target="_blank">Multiman</a> 自带FTP Server功能，默认设置下进入 Multiman 后 FTP Server 会自动开启，匿名即可登录进行上传下载操作。

  3. 进入XMB菜单下的 Install Package 目录安装pkg
REBUG CFG 在XMB的游戏菜单下有 Install Package目录，选中 fba-mm-ps3-R452.pkg 安装即可。

  4. 替换 EBOOT.bin 和 fbanext-ps3.xml
原版的pkg只支持3.55固件，所以要替换 EBOOT.bin 以支持4.30。首次运行FBAnext会在`/dev_hdd0/game/FBAN00000/USRDIR/`目录下生成名为 fbanext-ps3.xml 的配置文件，使用压缩包中的文件替换它的目的是设定外置ROM路径。

  5. 街机游戏 ROM 放在外置硬盘的 ROMS 或者 FBANext-ROMS 目录下
你也可以自定义 fbanext-ps3.xml中的配置语句来更改 ROM路径。上面的配置文件中有关 ROM路径的语句如下：

<pre lang='xml'>&lt;path>/dev_hdd0/game/ROMS00000/FBA/&lt;/path>
&lt;path>/dev_usb001/FBANext-ROMS/&lt;/path>
&lt;path>/dev_usb001/ROMS/&lt;/path>
</pre>

第一个是默认的内置硬盘路径。另外两个是外置硬盘路径，如果和实际情况有所差别，可以先做修改，然后上传覆盖。 </ol> 

### FBAnext的音视频设定

在FBAnext主界面下按 `SELECT` 键可以对视频和声音进行详细设定。据我的经验，**软件加速**和**三倍缓冲**是要开的，不然会很卡。因为配置是即时生效，所以如果对实际效果不满意，可以逐个尝试直到音视频都完美为止。

<div id="attachment_3754" style="width: 510px" class="wp-caption alignnone">
  <img src="http://digglife.qiniudn.com/wp-content/uploads/2014/02/ps3-fbanext-main-interface-500x281.jpg" alt="PS3街机模拟器FBAnext的主界面" width="500" height="281" class="size-medium wp-image-3754" />
  
  <p class="wp-caption-text">
    PS3街机模拟器FBAnext的主界面
  </p>
</div>

### 手柄按键设置

  1. 加载街机游戏ROM : `X`
  2. 根据机板筛选ROM : `L1/R1` 
      * 音视频等配置菜单 : `SELECT`
      * 重置当前游戏 : `R3` 
          * 回到已加载的游戏 : `START` 
              * 游戏中呼出上下文菜单 : `L1+R1+R2` 
            如果默认的键设定不合自己的习惯，可以在游戏中呼出上下文菜单选择 `Map Gamepad Buttons` 来自定义，其中SQUARE/CROSS/CIRCLE/TRIANGLE分别代表 □ × ○ ▲。
            
            <div id="attachment_3751" style="width: 510px" class="wp-caption alignnone">
              <img src="http://digglife.qiniudn.com/wp-content/uploads/2014/02/ps3-fbanext-context-menu-500x281.jpg" alt="FBAnext在游戏中的设定菜单" width="500" height="281" class="size-medium wp-image-3751" />
              
              <p class="wp-caption-text">
                FBAnext在游戏中的设定菜单
              </p>
            </div></ol> 
            
            ### 经典街机游戏ROMS下载
            
            网上有很多经典 CPS/NEOGEO 游戏ROM 下载，但是好像和PSP上的模拟器一样，需要事前做一些处理才能使用。下面是直接可用的一些经典街机ROM，包括 三国志/三剑圣，三国战记，恐龙新世纪，圆桌骑士，拳皇，合金弹头等等。
            
            [经典街机游戏ROMS百度盘下载][3]
            
            <div id="attachment_3753" style="width: 510px" class="wp-caption alignnone">
              <img src="http://digglife.qiniudn.com/wp-content/uploads/2014/02/ps3-fbanext-game-play-sankoku-500x281.jpg" alt="PS3上玩街机游戏三国战记" width="500" height="281" class="size-medium wp-image-3753" />
              
              <p class="wp-caption-text">
                PS3上玩街机游戏三国战记
              </p>
            </div>
            
            其实PS3上的双人横版过关游戏和格斗游戏是比较少的，和注重合家欢的 任天堂 不同，SONY 似乎有意忽视本地多人游戏以推广 PSN 多人联机，所以 PS3 上比较好玩的多半都是“枪车球”这三俗，玩腻歪了和小伙伴一起重温一下街机经典也是挺不错的。

 [1]: http://en.wikipedia.org/wiki/XrossMediaBar "PS3 XMB"
 [2]: http://rebug.me/ "PS3自制系统REBUG主页"
 [3]: http://pan.baidu.com/s/1gd85IIv "经典街机游戏ROMS百度盘下载"