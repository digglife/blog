---
title: Compiz Fusion新特效Stackswitch
author: 摩摩诘
type: post
date: 2008-06-22T08:05:56+00:00
url: /articles/add-compiz-fusion-stackswitch.html
comment_count:
  - 8
related_posts:
  - 'a:2:{s:4:"time";i:1224869424;s:13:"related_posts";s:1449:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/install-compiz-fusion-and-trouble-shooting-part2-2.html" title="Ubuntu Compiz Fusion安装和常见问题解决 Part.2">Ubuntu Compiz Fusion安装和常见问题解决 Part.2</a></li><li><a href="http://www.digglife.cn/articles/install-compiz-fusion-and-trouble-shooting-part1-2.html" title="Ubuntu Compiz Fusion安装和常见问题解决 Part.1">Ubuntu Compiz Fusion安装和常见问题解决 Part.1</a></li><li><a href="http://www.digglife.cn/articles/vista-task-tips.html" title="给Window XP添加Vista风格的任务栏预览">给Window XP添加Vista风格的任务栏预览</a></li><li><a href="http://www.digglife.cn/articles/%e5%9c%a8linux%e4%b8%8b%e4%bd%bf%e7%94%a8beryl%e5%ae%9e%e7%8e%b0vista%e6%95%88%e6%9e%9c.html" title="ubuntu 6.10 edgy beryl安装日志">ubuntu 6.10 edgy beryl安装日志</a></li><li><a href="http://www.digglife.cn/articles/vista-theme-visual-style-download.html" title="7个漂亮的Vista主题(视觉样式)下载">7个漂亮的Vista主题(视觉样式)下载</a></li><li><a href="http://www.digglife.cn/articles/wallpaper-windows7.html" title="9枚Windows 7高清壁纸">9枚Windows 7高清壁纸</a></li><li><a href="http://www.digglife.cn/articles/ubuntu-windows-xp-vista-firefox-profile.html" title="Ubuntu,Windows Vista和XP共享Firefox配置文件">Ubuntu,Windows Vista和XP共享Firefox配置文件</a></li></ul>";}'
views:
  - 2082
bot_views:
  - 2008
duoshuo_thread_id:
  - 1154125469839262075
categories:
  - Ubuntu技巧
tags:
  - compiz fusion
  - ubuntu
  - 特效
  - 美化

---
Stackswitch是Linux下的桌面特效软件 <a title="compiz fusion相关日志" href="https://www.digglife.net/articles/tag/compiz-fusion" target="_blank">Compiz Fusion</a> <a title="Just another switcher: Stackswitch" href="http://dev.compiz-fusion.org/~onestone/blog/?p=12" target="_blank">新推出</a>的一个窗口切换插件,之前与之类似的有Shift Switch,Ring Switch等.Switcher的功能在于能够让你在不同的窗口之间快速切换,相比<a title="Windows技巧" href="https://www.digglife.net/articles/category/windows-tricks" target="_blank">Windows</a> Vista下的Flip 3D,Compiz Fusion下的切换效果多种多样,而且效果非常夸张.Stackswitch也就是所谓的堆叠切换.

其具体效果如下:(点击查看大图)

<!--more-->

[<img style="vertical-align: text-bottom;" src="https://www.digglife.net/qiniu/2550/image/a030be541318573430265693773600b9.jpg" alt="Compiz Fusion新特效stackswitch截图" width="500" height="312" />][1]

**<a title="Ubuntu技巧" href="https://www.digglife.net/articles/category/about_ubuntu" target="_blank">Ubuntu</a> 8.04下的安装使用方法:**

1.安装Compiz Fusion最新版0.7.6

Ubuntu 8.04自带有0.7.4版本的Compiz Fusion,你需要升级到0.7.6版才能使用stackswitch.只需添加如下软件源,然后更新即可自动升级到0.7.6版本:<span style="color: #ff6600;">deb http://ppa.launchpad.net/compiz/ubuntu hardy main</span>

2.安装Stackswitch

打开新立得软件包管理器,搜索stackswich,标记并安装.

3.启用Stackswitch

打开compizconfig设置管理器,在窗口管理器栏目中找到stackswitch并启用,当然,你会碰到几个冲突选项,禁用目前使用的窗口切换特效即可.如果你还没有安装这个管理器,可以在新立得中标记安装<span style="color: #ff6600;">compizconfig-setting-manager</span>

4.使用Super+Tab键查看效果

有一段Youtube视频,有兴趣的可以先欣赏一下:
  


个人不推荐使用太多窗口特效,事实上我在Ubuntu下只是启用了最基本的&#8221;正常&#8221;级视觉效果,华丽的代价是效率低下.<a title="Compiz Fusion新特效Stackswitch" href="https://www.digglife.net/articles/add-compiz-fusion-stackswitch.html" target="_self">Stackswicth</a>这样的插件尝试一下就可以了.

 [1]: http://www.bababian.com/photozoom.sl?pictureid=BD37B7765B51650BF8257B56EC2F0BC8DT&size=5&viewID=B1E9FC10C6126F1235669209174F8D53UR "compiz fusion新特效stackswitch截图"
