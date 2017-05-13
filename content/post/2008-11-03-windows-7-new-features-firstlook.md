---
title: Windows 7新功能体验,这只是Pre Beta
author: 摩摩诘
type: post
date: 2008-11-03T10:22:10+00:00
url: /articles/windows-7-new-features-firstlook.html
index_image:
  - https://www.digglife.net/wp-content/uploads/2008/11/windows-7.jpg
views:
  - 5550
bot_views:
  - 2601
duoshuo_thread_id:
  - 1154125469839262174
categories:
  - Windows技巧
tags:
  - vista
  - windows
  - windows7

---
Windows 7的正式公开亮相应该是本年度底业界最有眼球吸引力的大事件，在PDC 2008上微软的工作人员向人们展示了Windows 7的许多新功能，大部分集中在用户界面和易用性方面，包括更加易用的任务栏和窗口管理，Library智能文件夹和Home Group的引入，资源管理器和全能搜索的改进，全新的Windows Solution Center和UAC管理机制，更加强大的设备管理组件等等。

昨天我下载并安装了Windows 7 Build 6801版本，这个版本和PDC2007上演示的版本并不一样，不少功能都没有或者有缺陷。最吸引人的任务栏功能没有激活，需要按照<a title="教您打开Windows 7 Build 6801的Superbar" href="http://www.cnbeta.com/articles/68682.htm" target="_blank">国外某强人的破解方法</a>激活(<a href="http://www.withinwindows.com/2008/11/02/flashy-windows-7-bits-protected-by-elaborate-scheme-workaround/" target="_blank">原英文链接</a>)，但是和PDC 2008上展示的还是有不小的区别。

<!--more-->

安装过程和Vista一样，装载镜像后安装到一个10GB左右的NTFS分区即可，注意，安装画面中的帮助文档显示的还是Windows Vista，大家不必理会，如果种子是在PDC 2008之后的，一般不会有假。**安装时间并没有比Vista快，完全启动的速度也并没有明显感觉有提升，而真正使用起来的速度也和Vista 感觉差不多（甚至感觉有些下降），所以在运行速度方面，大家暂时不用抱太大的希望，毕竟这是一个Alpha性质的预览版。**

至于那些在EeePC上安装Windows 7并号称十分流畅的朋友，我实在不明白，我只能理解为这是一种落差反应，对Vista失望太大，而对Windows 7的期望又太大，以至于心理出了点差错。

整体上感觉这些新功能看起来也许很有意思，但是真正用起来才觉得也不过如此，如果不能在系统性能上给人明显的提升，Windows 7还是不会让人满意的。下面是我体会比较深刻的几点。

### 1.任务栏和窗口管理

这个革命性的任务栏也许是Windows开发人员最能引以为豪的得意之作，尽管借鉴了<a title="Leopard" href="https://www.digglife.net/articles/tag/leopard" target="_blank">Mac OS X</a>上Dock的概念，但是在Windows上本土化得很好，并且新增了诸如**Jump List**之类的概念，所以还是比较有创意的。我们现在能够用到的，只是一个不完全版的任务栏，Jump List和桌面预览功能都无法体验到。不过这个工具栏在多窗口管理和寻找程序打开历史方面相比现有的这个任务栏还是方便不少。

<div id="attachment_2698" style="width: 622px" class="wp-caption aligncenter">
  <a href="https://www.digglife.net/wp-content/uploads/2008/11/taskbar.gif"><img class="size-full wp-image-2698 " title="Windows 7任务栏" src="http://digglife.qiniudn.com/wp-content/uploads/2008/11/taskbar.gif" alt="Windows 7 Build 6801下的任务栏有很多功能缺失" width="612" height="180" /></a>
  
  <p class="wp-caption-text">
    Windows 7 Build 6801下的任务栏有很多功能缺失
  </p>
</div>

 而改进后的状态栏也非常不错，我记得之前我还介绍过<a title="重排任务栏窗口和托盘图标工具Taskbar Shuffle" href="https://www.digglife.net/articles/rearrange-taskbar-and-system-tray-with-taskbar-shuffle.html" target="_blank">一个能够任意拖拽状态栏图标的软件</a>，而Windows 7已经内置了更好的状态栏管理，排列和隐藏都非常方便。

<div id="attachment_2701" style="width: 206px" class="wp-caption aligncenter">
  <a href="https://www.digglife.net/wp-content/uploads/2008/11/statusbar.gif"><img class="size-full wp-image-2701" title="Windows 7状态栏" src="http://digglife.qiniudn.com/wp-content/uploads/2008/11/statusbar.gif" alt="可以通过拖拽来排列通知区域图标" width="196" height="155" /></a>
  
  <p class="wp-caption-text">
    可以通过拖拽来排列通知区域图标
  </p>
</div>

Windows 7的网络连接管理的易用性相比之前是大有改善，不过和<a title="Ubuntu 8.10我体验到的新功能" href="https://www.digglife.net/articles/ubuntu-810-new-features.html" target="_blank">Ubuntu 8.10</a>相比感觉还是差了点，至少我没办法在状态栏从无线切换到有线。

<div id="attachment_2705" style="width: 343px" class="wp-caption aligncenter">
  <a href="https://www.digglife.net/wp-content/uploads/2008/11/wireless.gif"><img class="size-full wp-image-2705" title="Windows 7的无线管理" src="http://digglife.qiniudn.com/wp-content/uploads/2008/11/wireless.gif" alt="在状态栏即可查看和切换无线网络" width="333" height="407" /></a>
  
  <p class="wp-caption-text">
    在状态栏即可查看和切换无线网络
  </p>
</div>

在**多窗口管理**方面，Windows 7也新增了一些比较实用的小玩意。比如在拖拽窗口的时候，当鼠标碰到屏幕边缘（←↑→）会弹出一个透明的玻璃框，可以自动进行窗口缩放；点击任务栏最右端的显示桌面时所有窗口将只显示边框的功能似乎在6801里没有效果。

### 2.Windows Solution Center和UAC

Windows Solution Center是Windows安全中心的升级版本，除了包含以前的安全中心之外，还添加了系统维护（Maintenance）、问题解决（Trouble Shooting）和系统恢复（Systems Restore）。其中**“问题解决”模块估计都还在开发当中**，所以其下的所有功能都无法使用（显示为This parameter is incorrect）。这些新增的功能能否有效的帮助用户解决系统故障、提高系统的稳定性还有待以后的观察，至少，这个解决中心是非常必要的。

<div id="attachment_2702" style="width: 589px" class="wp-caption aligncenter">
  <a href="https://www.digglife.net/wp-content/uploads/2008/11/solution-center.gif"><img class="size-full wp-image-2702 " title="Windows 7的Windows Solution Center" src="http://digglife.qiniudn.com/wp-content/uploads/2008/11/solution-center.gif" alt="新增的Trouble Shooting还无法使用" width="579" height="380" /></a>
  
  <p class="wp-caption-text">
    新增的Trouble Shooting还无法使用
  </p>
</div>

Vista引入UAC本来是一件好事情，但是由于体验太差，最终成为一个被无数人诟病的大败笔。于是微软在Windows 7中已经了专门的UAC设置组件。

<div id="attachment_2704" style="width: 614px" class="wp-caption aligncenter">
  <img class="size-full wp-image-2704 " title="Windows 7的用户帐户管理" src="http://digglife.qiniudn.com/wp-content/uploads/2008/11/uac.gif" alt="4个UAC等级可供用户选择" width="604" height="606" />
  
  <p class="wp-caption-text">
    4个UAC等级可供用户选择
  </p>
</div>

Windows 7在默认状态下只在有程序试图对Windows设置做出改变的时候提醒用户，但是你还可以在4个等级之间调整UAC设置，包括“从不提醒”。这大大减小了UAC对用户体验的影响，不过在一定程度上也降低了UAC的作用。

### 3.资源管理器和搜索功能改进

**Windows 7的资源管理器更新包括简洁化的工具栏、针对图片视频等内容新增的“内容”查看方式、增强的搜索功能、Library智能文件夹等。**我用的时候觉得搜索的确是比Vista好用点了，过滤搜索结果更加快速，直接在提示框中点选过滤条件然后输入参数即可，我也一直觉得<a title="我最喜欢的Windows Vista功能" href="https://www.digglife.net/articles/my-favorite-vista-features.html" target="_blank">全能搜索是Vista最好的功能之一</a>。

Library文件夹和Mac OS里面的智能列表类似，方便对电脑和移动设备中文件进行**集中管理**，直接将硬盘或者移动设备中的文档、图片、视频、音乐文件夹链接到这里就可以随时进行搜索和管理了，和Home Group结合起来使局域网的分享更加方便。这是一个非常不错的改进。

<div id="attachment_2708" style="width: 610px" class="wp-caption aligncenter">
  <img class="size-full wp-image-2708 " title="Windows 7 Library和增强型全能搜索" src="http://digglife.qiniudn.com/wp-content/uploads/2008/11/search-library.gif" alt="搜索框下的过滤提示是一个很贴心的改进" width="600" height="370" />
  
  <p class="wp-caption-text">
    搜索框下的过滤提示是一个很贴心的改进
  </p>
</div>

### 4.总结

以上这些是我觉得比较显著的新功能，还有一个我觉得不错的Device Stage在这个预览版里也没能体验到，所以只好略过。至于Windows 7在视觉效果上的改进，Sidebar的废除，Windows Media Player升级到V12之类我觉得都不是什么大不了的新功能，这里就不说了。

Windows 7的这个预览版并不会给你太多的惊喜，在体验过程中我碰到多次Explorer.exe挂掉重启的情况，系统运行速度的确不能令人满意，而且经常出现卡住的情况，和Vista相比差了不少。但愿这只是Pre Pre Beta。