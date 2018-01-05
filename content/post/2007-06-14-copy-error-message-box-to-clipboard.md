---
title: 小技巧:如何复制Windows信息框文字到剪切板
author: 摩摩诘
type: post
date: 2007-06-14T09:46:27+00:00
url: /articles/copy-error-message-box-to-clipboard.html
comment_count:
  - 10
related_posts:
  - 'a:2:{s:4:"time";i:1224891295;s:13:"related_posts";s:1629:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/clean-up-desktop-improve-productivity-2.html" title="彻底清空桌面,让启动程序更加高效Part.2">彻底清空桌面,让启动程序更加高效Part.2</a></li><li><a href="http://www.digglife.cn/articles/clean-up-desktop-improve-productivity-1.html" title="彻底清空桌面,让启动程序更加高效Part.1">彻底清空桌面,让启动程序更加高效Part.1</a></li><li><a href="http://www.digglife.cn/articles/five-windows-explorer-tweaks.html" title="5大Windows Explorer优化技巧">5大Windows Explorer优化技巧</a></li><li><a href="http://www.digglife.cn/articles/copy-and-paste-with-middle-click.html" title="使用鼠标中键快速进行复制粘贴">使用鼠标中键快速进行复制粘贴</a></li><li><a href="http://www.digglife.cn/articles/windows%e5%b0%8f%e6%8a%80%e5%b7%a7%e5%a6%82%e4%bd%95%e6%8a%8a%e5%ae%89%e5%85%a8%e6%a8%a1%e5%bc%8f%e9%80%89%e9%a1%b9%e5%8a%a0%e5%85%a5%e5%90%af%e5%8a%a8%e8%8f%9c%e5%8d%95.html" title="Windows小技巧:如何把安全模式选项加入启动菜单">Windows小技巧:如何把安全模式选项加入启动菜单</a></li><li><a href="http://www.digglife.cn/articles/10-tips-of-windows-xp-average-users-dont-know.html" title="10个你可能不知道的Windows XP小技巧">10个你可能不知道的Windows XP小技巧</a></li><li><a href="http://www.digglife.cn/articles/%e9%85%b7%e8%bd%af%e6%8e%a8%e8%8d%90windows-explorer%e6%9d%80%e6%89%8bxplorer2.html" title="酷软推荐:Windows Explorer杀手,Xplorer2">酷软推荐:Windows Explorer杀手,Xplorer2</a></li></ul>";}'
bot_views:
  - 2346
views:
  - 3310
duoshuo_thread_id:
  - 1154125469839261812
categories:
  - Windows技巧
tags:
  - windows
  - 剪切版
  - 弹出窗口

---
看了之后你会发现这的确是个很简单的技巧,但是玩了这么久的电脑我居然一点都不知道.每次弹出无法理解的错误窗口时,我通常是自己将那些关键字打入搜索框搜索.没有想到还有直接Ctrl+C就可以直接将所有文字都复制到剪切板这个办法.看来Windows的小秘密还有待我进一步发现啊.

<font color="#ff0080">示意图:</font>

<a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/06/messagebox.png"><img width="450" src="http://digglife.qiniudn.com/wp-content/uploads/3/379/2007/06/messagebox-thumb.png" alt="messagebox" height="371" /></a>

<!--more-->

想简单地测试一下的话,开始&#8211;运行,任意输入一个Windows目录下没有的应用程序,Ok,必然会弹出一个找不到文件的弹出窗口.

弹出后**只需要按Ctrl+C就可以复制所有文字**了,如下:

> &#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;

> digglife

> &#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;

> Windows 找不到文件 &#8216;digglife&#8217;。请确定文件名是否正确后，再试一次。要搜索文件，请单击「开始」按钮，然后单击“搜索”。

> &#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;

> 确定  

> &#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;
>
> &#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;

不过这个方法目前只适合Windows的弹出信息框(Message Box),很多弹出窗口是应用程序的,对于那些,本方法不适用.不过其实也无所谓,我们主要就是要应付那些有点莫明其妙的类似乱码的信息而已&#8230;.比如这样的:

0x80040e09,内存不能为Read(一直觉得这句话很恶心&#8230;什么叫内存不能为&#8221;Read&#8221;,难道就不能翻译成内存不可读?)

来自<a target="_blank" href="http://www.lifehacker.com/software/windows-tip/copy-error-messages-text-to-the-clipboard-268547.php">LifeHacker</a>