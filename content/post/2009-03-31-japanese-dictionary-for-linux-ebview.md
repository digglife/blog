---
title: Linux下的日文词典EBView
author: 摩摩诘
type: post
date: 2009-03-31T15:54:05+00:00
url: /articles/japanese-dictionary-for-linux-ebview.html
index_image:
  - https://www.digglife.net/wp-content/uploads/IndexImage/dict.png
bot_views:
  - 2771
views:
  - 4376
duoshuo_thread_id:
  - 1154125469839262138
categories:
  - Ubuntu技巧
tags:
  - ebview
  - ebwin
  - Linux
  - ubuntu
  - 日文词典

---
EBView是一个跨平台的EBWING格式词典浏览工具，同时支持Windows和Linux，和我一直推荐的Windows下日文桌面词典<a title="最好的日文桌面电子词典EBWin更新到3.00" href="https://www.digglife.net/articles/japanese-edictionary-ebwin-update.html" target="_blank">EBWin</a>一样，EBView也具有体积小功能强的特点，只是在操作上可能不如EBWin那么直观，所以一直没有介绍。不过如果经常在Linux（比如Ubuntu）下工作，又需要一个日文词典，EBView就非常管用了。

EBView有很多自己的特点，比如后缀修正（搜索日语的活用形时非常有用）、多词典搜索、屏幕取词、自动复制、联网搜索、本地文件搜索等等，在功能上基本上不输给Windows下的EBWin。下面介绍Ubuntu下EBView的安装和使用方法。

<!--more-->

  1. 下载和安装
安装非常简单，在终端中输入<span style="color: #ff6600;">sudo apt-get install ebview</span>或者到新立得软件管理器中搜索安装都可以。安装完成后可以在“应用程序”－－“附件”中找到。

![EBWin词典搜索界面][1]

  2. 配置本地词典
EBView不能指定Catalog添加词典，不过方法更加简单，直接指定词典文件夹路径（Path）并设定好“搜索深度”（Deepth），然后点击“Search Disk”EBView就会自动将路径下所有的词典都添加进来，这个方法其实EBWin也支持，只是我们通常不用。

![EBWin配置本地词典][2]

EBView自动搜索到的结果可以进行编组分类，比如图中的普通词典和专业词典，这样可以避免使用多词典一次性搜索的时候太慢，另外也可以节约词典菜单空间。

没有词典文件的，可以查看这篇文章：<a title="EBPocket(EBWin)日文字典下载安装和使用教程" href="https://www.digglife.net/articles/ebpocket-ebwin.html" target="_blank">PPC:EBPocket(EBWin)日文字典下载安装和使用教程</a>

  3. 配置联网搜索
如果你想充分利用EBView提供的几十个词典搜索引擎，方便搜索无法在本地词典中找到的词语，可以配置一下外部浏览器。默认命令为<span style="color: #ff6600;">gnome-moz-remote％f</span>，但是这样是无法调用Firefox的，因为Ubuntu8.10并未安装gnome-bin，所以需要你自己安装，然后创建并配置[gnome-moz-remote][3]文件。

首先在终端中执行<span style="color: #ff6600;">sudo apt-get install gnome-bin</span>，然后执行以下命令：

<pre>gedit .gnome/gnome-moz-remote</pre>

并粘贴一段代码进去：

<pre>[Mozilla]
filename=firefox
NEEDS_TERM=false
NREMOTE=ture</pre>

保存后即可使用EBView的网页搜索功能了。EBView提供了完整的搜索引擎编辑工具，我们可以随时添加自己喜欢的词典搜索引擎。</ol> 

嗯，写完了。现在还有一个问题是，在EBWin里显示正常的中文在EBView中成了乱码，也就是说中日词典暂时不可用，不知道有没有什么好的解决办法。知道的请一定指教一下，[有关于][4]和[碎碎念][5]页面有我的联系方式。

[EBView主页][6]，[帮助页][6]中有详细的使用教程，值得阅读一下。

PS：EBWin昨天悄悄升级了一下，但是在功能上没有什么大变化，所以不升级也无所谓。

 [1]: https://www.digglife.net/qiniu/2967/image/3a5edecf60ac738bffecbc0e1019c012.png
 [2]: https://www.digglife.net/wp-content/uploads/archive/ebview-add-dic.png
 [3]: http://manpages.ubuntu.com/manpages/dapper/man1/gnome-moz-remote.1.html
 [4]: https://www.digglife.net/about
 [5]: https://www.digglife.net/twitter
 [6]: http://ebview.sourceforge.net/
