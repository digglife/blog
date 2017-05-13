---
title:
  - Ubuntu,Windows Vista和XP共享Firefox配置文件
author: 摩摩诘
type: post
date: 2008-07-18T10:01:47+00:00
url: /articles/ubuntu-windows-xp-vista-firefox-profile.html
description:
  - 我想许多朋友和我一样组建了双系统或者多系统,比如Windows XP,Windows Vista和Ubuntu并存在一台电脑上.如果我们在多个操作系统下都使用Firefox浏览器,在每一个平台下都使用不同的配置文件会很浪费也很没有效率.要是能够共享同一个配置文件,那么不但插件,扩展,收藏夹都能保持一致,而且保存的表单和密码等信息都能够在任意平台上使用,省时省力.
related_posts:
  - 'a:2:{s:4:"time";i:1224882254;s:13:"related_posts";s:1458:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/custom-windows-interface-tools.html" title="9个工具打造焕然一新的Windows界面">9个工具打造焕然一新的Windows界面</a></li><li><a href="http://www.digglife.cn/articles/clean-up-desktop-improve-productivity-2.html" title="彻底清空桌面,让启动程序更加高效Part.2">彻底清空桌面,让启动程序更加高效Part.2</a></li><li><a href="http://www.digglife.cn/articles/clean-up-desktop-improve-productivity-1.html" title="彻底清空桌面,让启动程序更加高效Part.1">彻底清空桌面,让启动程序更加高效Part.1</a></li><li><a href="http://www.digglife.cn/articles/free-clipboard-manager-clipx.html" title="小巧的Windows剪切板管理器:ClipX">小巧的Windows剪切板管理器:ClipX</a></li><li><a href="http://www.digglife.cn/articles/registry-searcher-editor-regscanner.html" title="免费好用的Windows注册表搜索编辑工具RegScanner">免费好用的Windows注册表搜索编辑工具RegScanner</a></li><li><a href="http://www.digglife.cn/articles/windows-linux-file-system.html" title="4款免费软件让你在Windows下访问Linux文件系统">4款免费软件让你在Windows下访问Linux文件系统</a></li><li><a href="http://www.digglife.cn/articles/faster-copy-windows.html" title="加快Windows下的文件复制速度:TeraCopy">加快Windows下的文件复制速度:TeraCopy</a></li></ul>";}'
views:
  - 4287
bot_views:
  - 2802
syntaxhighlighter_encoded:
  - 1
duoshuo_thread_id:
  - 1154125469839262097
categories:
  - Ubuntu技巧
tags:
  - ubuntu
  - windows
  - 火狐技巧
  - 软件
  - 配置文件

---
我想许多朋友和我一样组建了双系统或者多系统,比如<a title="Windows技巧" href="https://www.digglife.net/articles/category/windows-tricks" target="_blank">Windows</a> XP,Windows Vista和<a title="Ubuntu技巧" href="https://www.digglife.net/articles/category/about_ubuntu" target="_blank">Ubuntu</a>并存在一台电脑上.如果我们在多个操作系统下都使用<a title="火狐技巧" href="https://www.digglife.net/articles/category/firefox" target="_blank">Firefox</a>浏览器,在每一个平台下都使用不同的配置文件会很浪费也很没有效率.要是能够共享同一个配置文件,那么不但插件,扩展,收藏夹都能保持一致,而且保存的表单和密码等信息都能够在任意平台上使用,省时省力.当然,如果你在各个操作系统下都安装了<a title="一周Firefox扩展推荐-第一辑" href="https://www.digglife.net/articles/firefox-addons-weekly-issue1.html" target="_blank">Mozilla实验室的Weave</a>也能基本实现同样的效果,但是很遗憾的是,用过的都知道Mozilla这个扩展目前还没能达到值得信赖的程度.

<!--more-->

下面介绍一下这个方法,熟悉Firefox配置文件管理的朋友应该也能够想象到如何做.首先,我们应该了解这3个操作系统中Firefox配置文件所在的路径:

  * Windows Vista:Users\<UserName>\AppData\Roaming\Mozilla\Firefox
  * Windows XP/2000/2003:Documents and Settings\<UserName>\Application Data\Mozilla\Firefox
  * Linux:~/.mozilla/firefox

知道了这些,我们用Firefox的配置文件管理器就能实现跨操作系统共享了.

以Ubuntu共享Windows XP的Firefox配置文件为例:

1.关闭Firefox,在终端中输入<span style="font-family: Courier New; color: #ff5a00;">firefox -profilemanager</span>,这时会弹出配置文件管理界面.

<img class="aligncenter" title="Firefox配置文件管理器" src="http://digglife.qiniudn.com/wp-content/uploads/archive/Firefox%20-%20Choose%20User%20Profile.png" alt="" width="385" height="288" />

2.点击创建配置文件(Create A New Profile),然后在弹出窗口中点击选择文件夹(Choose Folder),定位到<span style="font-family: Courier New; color: #ff5a00;">Documents and Settings/<你的用户名>/Application Data/Mozilla/Firefox/Profiles</span>,选择以.default结尾的那个文件夹(我不确定大家的文件夹名是不是一样的).

<div style="width: 410px" class="wp-caption aligncenter">
  <a href="http://picasaweb.google.com/digglifeshow/oCzYfC/photo#5224287886248586466"><img title="创建Firefox配置文件" src="http://digglife.qiniudn.com/wp-content/uploads/archive/Create%20Profile%20Wizard.png" alt="" width="400" height="298" /></a>
  
  <p class="wp-caption-text">
    给配置文件命名,并点击Choose File
  </p>
</div>

<div style="width: 410px" class="wp-caption aligncenter">
  <a href="http://picasaweb.google.com/digglifeshow/oCzYfC/photo#5224287883699916802"><img title="定位到Windows XP下的Firefox配置文件夹" src="http://digglife.qiniudn.com/wp-content/uploads/archive/Choose%20Profile%20Folder.png" alt="定位到Windows XP下的Firefox配置文件夹" width="400" height="312" /></a>
  
  <p class="wp-caption-text">
    定位到Windows XP下的Firefox配置文件夹
  </p>
</div>

3.如果你想一直使用Windows下的配置文件,可以够选启动时不用询问(Don&#8217;t ask at starup).

注1:如果要共享Windows Vista的配置文件,第二步中的配置文件路径应该改为<span style="font-family: Courier New; color: #ff5a00;">users\<你的用户名>\AppData\Roaming\Mozilla\Firefox\Profiles\</span>

注2:在Windows下打开配置文件管理器的步骤是:运行(Win+R)&#8211;输入firefox.exe -profilemanager,如果你的Firefox不是安装在默认目录下,这条命令应修改为<span style="font-family: Courier New; color: #ff5a00;">firefox所在路径\firefox.exe -profilemanager</span>.

这样的方法可能会造成一些扩展的不兼容,比如IE Tab和Google Toolbar就不能兼容Ubuntu.不过好在并没有太大影响,具体的利害得失,朋友们自己权衡吧.我现在Vista和Ubuntu都共享XP下的配置文件了.