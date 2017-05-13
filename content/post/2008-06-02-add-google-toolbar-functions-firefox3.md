---
title: 给Firefox 3添加Google Toolbar的功能
author: 摩摩诘
type: post
date: 2008-06-02T11:14:31+00:00
url: /articles/add-google-toolbar-functions-firefox3.html
comment_count:
  - 12
trackback_count:
  - 1
related_posts:
  - 'a:2:{s:4:"time";i:1224860454;s:13:"related_posts";s:1193:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/firefox-addons-new-site.html" title="Firefox 3附加软件页面预览">Firefox 3附加软件页面预览</a></li><li><a href="http://www.digglife.cn/articles/firefox-addons-weekly-issue3.html" title="一周Firefox扩展推荐-第三辑">一周Firefox扩展推荐-第三辑</a></li><li><a href="http://www.digglife.cn/articles/firefox-addons-weekly-issue2.html" title="一周Firefox扩展推荐-第二辑">一周Firefox扩展推荐-第二辑</a></li><li><a href="http://www.digglife.cn/articles/firefox-addons-weekly-issue1.html" title="一周Firefox扩展推荐-第一辑">一周Firefox扩展推荐-第一辑</a></li><li><a href="http://www.digglife.cn/articles/social-web-firefox-yoono.html" title="社会化浏览器扩展Yoono">社会化浏览器扩展Yoono</a></li><li><a href="http://www.digglife.cn/articles/firefox3-themes-download-windows-mac.html" title="Windows XP,Vista和Mac版Firefox 3主题下载">Windows XP,Vista和Mac版Firefox 3主题下载</a></li><li><a href="http://www.digglife.cn/articles/firefox3-download-day.html" title="Go Go Go!Firefox 3!">Go Go Go!Firefox 3!</a></li></ul>";}'
views:
  - 2838
bot_views:
  - 2511
duoshuo_thread_id:
  - 1154125469839262070
categories:
  - 火狐技巧
tags:
  - firefox 3
  - google
  - google工具栏
  - 扩展

---
Google Toolbar For <a title="Firefox" href="https://www.digglife.net/articles/category/firefox" target="_blank">Firefox</a>开发团队的进度实在太慢,到现在还没有发布For <a title="Firefox 3" href="https://www.digglife.net/articles/tag/firefox-3" target="_blank">Firefox 3</a>的新版本,许多重度依赖用户比如我一时难以适应.照目前的情况看来,Google可能会在Firefox 3正式版推出一段时间后才会更新,所以我们只好通过其他途径来实现<a title="使用Google工具栏的十个理由" href="https://www.digglife.net/articles/10-reasons-for-using-google-toolbar.html" target="_blank">Google Toolbar的一些常用功能</a>.当然,<a title="给Firefox 3添加Google Toolbar的功能" href="https://www.digglife.net/articles/add-google-toolbar-functions-firefox3.html" target="_blank">下面的方法</a>可能比之安装一个Google工具栏扩展要麻烦,但是聊胜于无,作为过渡还是可以的.

**Update:**Google Toolbar已经有兼容Firefox 3的版本,请移步[Google Toolbar主页][1]下载.或者直接点击下面链接下载:

[Google Toolbar Windows版][2]

<a title="Google toolbar For Linux版" href="http://dl.google.com/firefox/google-toolbar-ff3-linux.xpi" target="_self">Google Toolbar Linux版</a>

<!--more-->

**1.字词翻译器.**

这个功能可能是许多用户最依赖的功能,Google的翻译反应快,界面简单,在阅读英文文章的时候很方便.我一直没有发现比较好的替代扩展,划词搜索这种模式我想没有几个人能够忍耐.好在<a title="谷歌金山词霸" href="http://g.iciba.com/" target="_blank">谷歌金山词霸</a>在前些天的更新中新增了Firefox 3的支持,尽管相比Google即时翻译还是太繁琐,但是基本可以接受.

**2.添加搜索类型**

其实Firefox 2就有这样的功能,只不过没有Google Toolbar来的直观.我们可以通过在搜索框点击右键&#8211;添加搜索关键字的方法为Firefox添加搜索引擎,以后只要在Awesome Bar中输入&#8221;搜索关键字+空格+查询内容&#8221;即可.某些搜索引擎支持<a title="Open Search声明格式" href="http://www.opensearch.org/Home" target="_blank">Open Search声明格式</a>(比如优酷,Firefox Addons等),这时你会发现Firefox搜索框有时会在下拉箭头处显示一个蓝色的圆圈,点击会在菜单中发现添加某某搜索引擎的提示,点击即可添加该搜索引擎.

![添加支持Open Search的搜索引擎][3]

如果你希望添加任意搜索引擎到Firefox搜索框,可以安装<a title="Add To Search Bar" href="https://addons.mozilla.org/en-US/firefox/addon/3682" target="_blank">Add To Search Bar</a>这个扩展,还可以自定义Favicon.以后直接<span style="font-family: Courier New;">Ctrl+K</span>跳转到搜索框,和Google工具栏一样方便.

![添加任意搜索引擎][4]

**3.Google Bookmark**

这个也是我一直使用Google Toolbar的原因,我的书签都整理在Google Bookmarks,完全是一种习惯,改不过来.我们可以安装<a title="Gmarks" href="https://addons.mozilla.org/en-US/firefox/addon/2888" target="_blank">Gmarks</a>扩展实现,而且功能要比Google工具栏自带的要方便.具体如何方便,大家可以自己体验.

![Gmarks选项][5]

**4.Pagerank显示**

安装<a title="Search Status" href="https://addons.mozilla.org/en-US/firefox/addon/321" target="_blank">Search Status</a>扩展即可,这个扩展除了显示Pagerank和Alexa Rank之外还有许多实用功能.

![Search Status选项][6]

**5.搜索字词标明**

很方便的一个功能,让我们搜索之后不用睁大眼睛满页寻找搜索关键字.这个功能我们可以通过安装<a href="https://addons.mozilla.org/en-US/firefox/addon/376" target="_blank">SearchWP</a>扩展实现.

![高亮搜索关键字][7]

**6.其他功能**

寻字按钮,订阅供稿,拼写检查等功能Firefox 2就能够实现,Firefox 3也有了许多改进,不必依赖Google工具栏.

如果你习惯了点击Google工具栏自定义按钮进入某网站,不妨启用Google书签工具栏,将常用网站装进几个文件夹放在书签工具栏,我最近也逐渐开始学着使用这个之前不怎么使用的工具条了,其实也非常方便,如果嫌这个工具栏占用了浏览空间,不妨安装一个Hide Menu扩展.Google Doc自动链接功能其实也很方便,不知道能不能通过修改<span style="font-family: Courier New;">about:config</span>里面的参数实现.

估计等到Google工具栏Firefox3版出现的时候,我已经不想用了.其实这次的更新我期待的是和IE版本的工具栏一样,能够将设置和按钮存储在Google的服务器上,还有完全可以媲美<a title="IE 8 Beta 1简体中文版下载和新功能介绍" href="https://www.digglife.net/articles/ie8-new-features-download.html" target="_blank">IE 8 WebSlices</a>的新版Google工具栏按钮.

 [1]: http://www.google.com/tools/firefox/toolbar/ "Google Toolbar主页"
 [2]: http://dl.google.com/firefox/google-toolbar-ff3-win.xpi "Google toolbar For Windows版"
 [3]: http://digglife.qiniudn.com/qiniu/2541/image/83de422513a378b774f61c096441b590.jpg
 [4]: http://digglife.qiniudn.com/qiniu/2541/image/1b3cd3ff16dc79c792b8f492cc2a0f57.jpg
 [5]: http://digglife.qiniudn.com/qiniu/2541/image/8aca7fbe168bd6ee873c21ab393b4cd1.jpg
 [6]: http://digglife.qiniudn.com/qiniu/2541/image/2baf9ad9201d767cece88a545624db87.jpg
 [7]: http://digglife.qiniudn.com/qiniu/2541/image/112887da90bd40a49ab4474cb7d64f22.jpg