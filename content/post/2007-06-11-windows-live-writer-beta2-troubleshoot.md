---
title: Windows Live Writer 2无法安装和资源占用过高的解决方案
author: 摩摩诘
type: post
date: 2007-06-11T08:27:04+00:00
url: /articles/windows-live-writer-beta2-troubleshoot.html
0:
  - 6f8c4077d0de2ac381137a51048f750aec70518fa7a2c1667c39248c5d2895531d2c651212594c85fb30f54ac022709f
  - 6f8c4077d0de2ac381137a51048f750aec70518fa7a2c1667c39248c5d2895531d2c651212594c85fb30f54ac022709f
1:
  - 12c028852d86dc2a5738742462e8e633741b33a3309c4811f503fb0e20f157852449ef21d9976d79ebecd8413895fadd
  - 12c028852d86dc2a5738742462e8e633741b33a3309c4811f503fb0e20f157852449ef21d9976d79ebecd8413895fadd
comment_count:
  - 3
related_posts:
  - 'a:2:{s:4:"time";i:1224865018;s:13:"related_posts";s:1360:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/windows-live-writer-tricks-and-tips-2.html" title="我的Windows Live Writer使用心得 Part.2">我的Windows Live Writer使用心得 Part.2</a></li><li><a href="http://www.digglife.cn/articles/windows-live-writer-tricks-and-tips.html" title="我的Windows Live Writer使用心得 Part.1">我的Windows Live Writer使用心得 Part.1</a></li><li><a href="http://www.digglife.cn/articles/backup-windows-live-writer.html" title="如何全面备份Windows Live Writer">如何全面备份Windows Live Writer</a></li><li><a href="http://www.digglife.cn/articles/firstlook-of-windows-live-writer-beta3.html" title="Windows Live Writer Beta 3安装和试用">Windows Live Writer Beta 3安装和试用</a></li><li><a href="http://www.digglife.cn/articles/windows-live-writer-beta2-released.html" title="Windows Live Writer Beta2发布.">Windows Live Writer Beta2发布.</a></li><li><a href="http://www.digglife.cn/articles/can-not-modify-category-slug.html" title="Wordpress无法编辑分类缩略名(Slug)的解决">Wordpress无法编辑分类缩略名(Slug)的解决</a></li><li><a href="http://www.digglife.cn/articles/enjoy-wlw-technical-preview.html" title="Window Live Writer技术预览版下载和体验">Window Live Writer技术预览版下载和体验</a></li></ul>";}'
bot_views:
  - 1925
views:
  - 982
duoshuo_thread_id:
  - 1154125469839261808
categories:
  - 博客研究
tags:
  - windows live writer
  - 微软

---
<a href="https://www.digglife.net/articles/windows-live-writer-beta2-released.html" target="_blank">Windows Live Writer Beta 2上周发布</a>后用户反应了很多问题,<a href="https://www.digglife.net/wp-content/uploads/3/379/2007/06/wlw-cr.png" atomicselection="true"><img style="border-top-width: 0px; border-left-width: 0px; border-bottom-width: 0px; border-right-width: 0px" height="47" alt="WLW_cr" src="https://www.digglife.net/wp-content/uploads/3/379/2007/06/wlw-cr-thumb.png" width="240" align="right" border="0" /></a>包括无法安装和造成资源占用过高导致电脑宕机.今天WLW团队在他们的博客<a href="http://windowslivewriter.spaces.live.com/" target="_blank">Writer Zone</a>上提供了官方的解决办法.

&nbsp;

**问题一: WLW安装失败.**

**症状:**

安装Writer的时候,安装进程无法完成或者要花很长时间.

**故障原因:**

如果你想在已经安装有Windows Live Writer,Windows Live Mail,Window Live Messenger其他语言版本的电脑上直接安装Windows Live Wirter beta 2,因为这些语言版本的Intaller会自动阻止安装进行(即便你卸载该程序后依然如此),所以会导致无法安装.

**解决办法:**

****&nbsp;

卸载阻止Writer安装的Installer,并将记录发送至[support team][1].

1. 在桌面上新建一个名为**Log Files**的文件夹.

2. 复制3个Log文件到该文件夹

Windows XP SP2用户定位到以下文件夹:

>   * C:\Documents and Settings\All Users\Application Data\WindowsLiveInstaller\logs
>   * C:\Documents and Settings\All Users\Application Data\WindowsLiveInstaller\MsiLogs
>   * C:\Documents and Settings\All Users\Application Data\WLInstaller

<!--more-->

WindowsVista 用户定位到以下文件夹获取:

>   * C:\programdata\WindowsLiveInstaller\logs
>   * C:\programdata\WindowsLiveInstaller\MsiLogs
>   * C:\programdata\WLInstaller

3. 点击下载<a href="http://download.microsoft.com/download/2/3/0/23036331-516d-4c7e-b9ac-31554a2fec06/WL-Beta-remove.zip" target="_blank">WL-Beta-Remove</a>文件.

4.保存链接指向的Zip文件到桌面.

<a href="https://www.digglife.net/wp-content/uploads/3/379/2007/06/wl-beta-remove.jpg" atomicselection="true"><img height="316" alt="Wl-beta-remove" src="https://www.digglife.net/wp-content/uploads/3/379/2007/06/wl-beta-remove-thumb.jpg" width="450" /></a>

5.打开**WL-Beta-remove.zip**.

6. 解压所有文件到桌面.

7. 打开**WL-Beta-remove** 文件夹(内部会有一个名为**WL-Beta-Remove.cmd**的文件).

8. 双击**WL-Beta-Remove.cmd**.

9. 点击执行.

<a href="https://www.digglife.net/wp-content/uploads/3/379/2007/06/command.jpg" atomicselection="true"><img height="315" alt="command" src="https://www.digglife.net/wp-content/uploads/3/379/2007/06/command-thumb.jpg" width="450" /></a>

10. 重新安装Windows Live Writer.&nbsp; NOTE: 如果你还安装有Windows Live Messenger 或者Windows Live Mail ,你还需要一并重装他们:

  * 重新安装<a href="http://get.live.com/betas/maildesktop_betas" target="_blank">Windows Live Mail</a>
  * 重新安装<a href="http://get.live.com/betas/messenger_betas" target="_blank">Windows Live Messenger</a>

11. 打开[Writer support page][1] 并提交第二步保存的记录文件.

12. 删除桌面上所有上面新创建的文件夹

**问题二:运行WLW的时候系统宕机**

**症状:**

打开WLW导致系统没有响应.在Windows 任务管理器里面,一个svchost.exe进程CPU占用为100%.(注意:一旦系统没有响应Windows 任务管理器也将无法打开,所以你需要在打开WLW之前开启任务管理器.)

**原因:**

当WLW打开的时候,他会自动执行Windows Live Setup 服务检查更新.在某些配置下,这种特殊的升级检查算法会导致该症状发生.

**解决办法**

禁用Windows Live Writer升级服务:

1. 在开始菜单中点击&#8221;运行&#8221;(Win+R).

2. 输入&#8221;cmd&#8221;并运行.

<a href="https://www.digglife.net/wp-content/uploads/3/379/2007/06/run.jpg" atomicselection="true"><img height="226" alt="run" src="https://www.digglife.net/wp-content/uploads/3/379/2007/06/run-thumb.jpg" width="450" /></a>

3. 在命令提示符程序中输入一下命令:

  * net stop &#8220;Windows Live Setup Service&#8221;
  * 回车
  * sc config &#8220;Windows Live Setup Service&#8221; start=disabled
  * 回车

4. 关闭命令提示符和其他运行的程序

5.&nbsp;重启电脑

6. 启动Windows Live Writer.

如果你还有什么问题,可以联系<a href="http://support.live.com/eform.aspx?productKey=wlwriter&page=wlsupport_home_options_form_byemail&ct=eformts" target="_blank">WLW支持中心</a>,或者访问<a href="http://windowslivewriter.spaces.live.com/" target="_blank">他们的博客</a>.

附上简体中文windows live writer beta2下载地址:

<a href="http://download.microsoft.com/download/1/e/c/1ecbf3be-298b-467c-84d8-6f86f01478d7/ZH-CN/Install_WLWriter.exe" target="_blank">WLW beta 2 Chinese Version</a>

 [1]: http://support.live.com/eform.aspx?productKey=wlwriter&page=wlsupport_home_options_form_byemail&ct=eformts
