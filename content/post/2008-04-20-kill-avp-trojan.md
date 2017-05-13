---
title: avp.exe木马(NSIS Error)解决方案
author: 摩摩诘
type: post
date: 2008-04-20T03:39:40+00:00
url: /articles/kill-avp-trojan.html
0:
  - wpAjax296db54a5c79a4e91d1e89b899ab2c0f5823f3a7529eb23a76ca836ae1172f060e35741ae7e4ba7b593ba2d454f58450
comment_count:
  - 2
related_posts:
  - 'a:2:{s:4:"time";i:1224889816;s:13:"related_posts";s:240:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/virus-equals-windows-to-apple.html" title="Virus=Windows,苹果官网对Windows的恶搞">Virus=Windows,苹果官网对Windows的恶搞</a></li></ul>";}'
bot_views:
  - 2824
views:
  - 8324
duoshuo_thread_id:
  - 1154125469839262053
categories:
  - Windows技巧
tags:
  - avp
  - 木马
  - 杀毒
  - 病毒

---
前几天<a href="http://nihonmessage.yo2.cn" target="_blank">日网些事</a>的博主北极小鱼同学的电脑中了一个非常无耻的木马avp.exe,杀不掉,重装系统之后依然存在,直接导致了他更新暂停,也让我不得安宁.当时发现这个病毒的时候在网上搜索到了很多相关文章,但是都无法彻底解决.前天终于在<a href="http://baike.360.cn/4005462/3973267.html?page=184" title="360安全卫士论坛" target="_blank">360安全卫士论坛</a>找到了一个比较完美的解决方案.

<!--more-->

avp.exe木马的主要特征是:

  1. 资源管理器中会出现一个avp.exe进程,有时会<strike>咱用</strike>占用较大的系统资源.(注意,这个avp.exe并不是卡巴斯基的进程)
  2. 系统分区的根目录会出现avp.exe文件,删除之后会自动恢复.
  3. 大部分安装文件(主要是.exe文件)无法运行,会弹出一个文件已损坏的NSIS Error错误对话框.

![][1]

有些中毒电脑上还会有其他文件,比如Ver.txt等等.不过貌似都可以用同样的方式解决.

首先祭出<a href="http://dl.360safe.com/killer_ati2evxx.exe" title="360的专杀工具ati2evxx" target="_blank"><strong>360的专杀工具ati2evxx</strong></a>,这个专杀工具能够彻底清除avp.exe

如果被感染的exe文件还是不能运行,继续提示NSIS错误,那就没有办法了,只能删除这些文件.如果你知道病毒感染的日期,可以搜索当天被更改的exe文件,然后全部删除即可.

**所以最彻底的解决办法是:使用专杀工具清除&#8211;删除被感染的exe文件&#8211;重做系统.**

这个木马的破坏性极大,已经好久没有碰到类似的垃圾了.大家用电脑还是小心为妙啊,重在防御,等你发现已经中标的时候,大部分时候都为时已晚.

 [1]: http://digglife.qiniudn.com/qiniu/2495/image/3b009e6139b85b9a23736da05cf115f6.jpg