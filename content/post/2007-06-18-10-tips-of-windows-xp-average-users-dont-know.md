---
title:
  - 10个你可能不知道的Windows XP小技巧
  - 10个你可能不知道的Windows XP小技巧
author: 摩摩诘
type: post
date: 2007-06-18T09:42:14+00:00
url: /articles/10-tips-of-windows-xp-average-users-dont-know.html
0:
  - c0c4a4a5611442eadfd24457a29bc6fc524ae09a3cab3bb23f4d156ea207e9b8cc9624b243264c5320f8891b5549fe06
  - c0c4a4a5611442eadfd24457a29bc6fc524ae09a3cab3bb23f4d156ea207e9b8cc9624b243264c5320f8891b5549fe06
comment_count:
  - 6
related_posts:
  - 'a:2:{s:4:"time";i:1224880836;s:13:"related_posts";s:1641:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/clean-up-desktop-improve-productivity-2.html" title="彻底清空桌面,让启动程序更加高效Part.2">彻底清空桌面,让启动程序更加高效Part.2</a></li><li><a href="http://www.digglife.cn/articles/clean-up-desktop-improve-productivity-1.html" title="彻底清空桌面,让启动程序更加高效Part.1">彻底清空桌面,让启动程序更加高效Part.1</a></li><li><a href="http://www.digglife.cn/articles/five-windows-explorer-tweaks.html" title="5大Windows Explorer优化技巧">5大Windows Explorer优化技巧</a></li><li><a href="http://www.digglife.cn/articles/copy-and-paste-with-middle-click.html" title="使用鼠标中键快速进行复制粘贴">使用鼠标中键快速进行复制粘贴</a></li><li><a href="http://www.digglife.cn/articles/windows%e5%b0%8f%e6%8a%80%e5%b7%a7%e5%a6%82%e4%bd%95%e6%8a%8a%e5%ae%89%e5%85%a8%e6%a8%a1%e5%bc%8f%e9%80%89%e9%a1%b9%e5%8a%a0%e5%85%a5%e5%90%af%e5%8a%a8%e8%8f%9c%e5%8d%95.html" title="Windows小技巧:如何把安全模式选项加入启动菜单">Windows小技巧:如何把安全模式选项加入启动菜单</a></li><li><a href="http://www.digglife.cn/articles/copy-error-message-box-to-clipboard.html" title="小技巧:如何复制Windows信息框文字到剪切板">小技巧:如何复制Windows信息框文字到剪切板</a></li><li><a href="http://www.digglife.cn/articles/%e9%85%b7%e8%bd%af%e6%8e%a8%e8%8d%90windows-explorer%e6%9d%80%e6%89%8bxplorer2.html" title="酷软推荐:Windows Explorer杀手,Xplorer2">酷软推荐:Windows Explorer杀手,Xplorer2</a></li></ul>";}'
views:
  - 1210
bot_views:
  - 1575
duoshuo_thread_id:
  - 1154125469839261815
categories:
  - Windows技巧
tags:
  - windows
  - XP
  - 十大

---
**1.查看完整的系统信息.**

开始&#8211;运行&#8211;输入&#8221;command&#8221;,在命令提示符里面输入&#8221;Systeminfo&#8221;,系统将会检测电脑的多项有用信息,你的基本硬件信息,操作系统版本,甚至是补丁记录.如果你想保存这些记录,可以输入&#8221;Systeminfo>info.txt&#8221;,生成的文件视你输入该命令时所在的目录而定.

<a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/06/systeminfo.png"><img width="450" src="http://digglife.qiniudn.com/wp-content/uploads/3/379/2007/06/systeminfo-thumb.png" alt="systeminfo" height="232" /></a>

<!--more-->

**2.直接彻底删除文件.**

其实很多情况下放到回收站的东西我们会不再理睬的,所以为了免去清空回收站的步骤,可以做如下设置.开始&#8211;运行&#8211;输入&#8221;gpedit.msc&#8221;.定位到:用户配置-管理面板-windows组件-windows资源管理器,在右边栏找到&#8221;不要将已删除的文件移动到回收站&#8221;,双击并启用.

<a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/06/recyclebin.png"><img width="450" src="http://digglife.qiniudn.com/wp-content/uploads/3/379/2007/06/recyclebin-thumb.png" alt="recyclebin" height="307" /></a>

另外一种方法是:直接右键点击回收站,选择属性,在全局设置中选中&#8221;删除时不将文件移入回收站,而是直接删除&#8221;.如果你已经按照上一种方法设置,那么,所有的选项将为灰色.

<a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/06/recyclebin2.png"><img width="344" src="http://digglife.qiniudn.com/wp-content/uploads/3/379/2007/06/recyclebin2-thumb.png" alt="recyclebin2" height="395" /></a>

**3.双击锁定电脑.**

在桌面上空白处点击右键&#8211;新建,创建一个新快捷方式,在&#8221;请输入项目的位置下&#8221;输入&#8221;&#8216;rundll32.exe user32.dll,LockWorkStation&#8221;,然后给它任意取个你喜欢的名字.OK,双击这个快捷方式,测试一下.当然,直接按**组合键Win+L**可以达到同样效果.

<a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/06/lockworkstation.png"><img width="450" src="http://digglife.qiniudn.com/wp-content/uploads/3/379/2007/06/lockworkstation-thumb.png" alt="lockworkstation" height="308" /></a> 

**4.删除系统隐藏程序.**

XP隐藏了许多系统程序,比如Windows Messager,你可以让它变得可见.定位到/windows/inf/sysoc.inf,使用记事本文档或其他文本编辑器打开,查找&#8221;hide&#8221;并将其删除(有多个).现在你可以进入添加删除程序,点击添加删除Windows组件,是不是看到很多以前没有的项目呢?嗯,现在你可以删除它们了,不过注意,你需要确定他们的用途后根据自己的需要删除,以免造成Windows系统出错.

**5. 一些有趣的命令.**

如果你非常喜欢使用命令行,这里有一些你也许不知道命令.比如:

&#8220;eventcreate&#8221;创建系统事件.

&#8220;eventtriggers&#8221;查看系统事件.

&#8220;typeperf&#8221;查看子系统性能.

&#8220;schtasks&#8221;组织系统计划任务.

和平常一样,你可以在命令后加&#8221; /?&#8221;来查看命令的用法.

**7.使用命令行代替任务管理器.**

你可以使用&#8221;taskkill&#8221;或者&#8221;takill&#8221;命令来杀死系统进程,用法是&#8221;taskkill 进程ID&#8221;,可以使用&#8221;tasklist&#8221;命令来显示所有进程的状态和ID号.这对于杀死一些不会显示在任务管理器的病毒进程尤其有效,

**8.使用Windows默认程序打开Zip文件**.

对于Zip文件,Windows XP能够像打开文件夹一样打开它,这个功能对于机器比较老的用户尤其有用.你可以在运行栏中键入&#8221;regsvr32 /u zipfldr.dll&#8221;让Windows XP单独处理Zip文件,其他的压缩包关联不会变.还原设置键入&#8221;regsvr32 zipfldr.dll&#8221;.

<a atomicselection="true" href="https://www.digglife.net/wp-content/uploads/3/379/2007/06/zipfolders.png"><img width="450" src="http://digglife.qiniudn.com/wp-content/uploads/3/379/2007/06/zipfolders-thumb.png" alt="zipfolders" height="248" /></a>

**9.禁用提示气泡.**

Windows的这些提醒很烦,如果你非常熟悉它们,那么禁用它吧.开始,运行,输入Regedit.定位到HKEY\_CURRENT\_USER/Software/Microsoft/Windows/Current Version/Explorer/Advanced,创建一个叫做&#8221;EnableBallonTips&#8221;的DWORD值,并将赋值为0.

**10.重命名多个文件**.

可能有些人认为Windows不允许文件名重复,所以不会提供多文件重命名功能.但是事实上的确可以,特别是你在编辑某个主题相同的文件群时,这个功能特别有用.选择你想重命名的多个文件,右键点击,选择重命名,输入文件名,Windows会自动给他们加上独特的数字编号.

原文来自<a target="_blank" href="http://www.clipmarks.com/view_clip.aspx?guid=A257968B-1247-46B8-8EAE-DF41C02E9D90">Clipmark</a>,有20条

[<img border="0" src="http://digglife.qiniudn.com/qiniu/1066/image/90e0e97427652cf8dd6388aaabac91cb.jpg" alt="Hit Tracker" />][1]

 [1]: http://www.ritecounter.com