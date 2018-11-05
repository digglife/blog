---
title: 我的Windows Live Writer使用心得 Part.1
author: 摩摩诘
type: post
date: 2007-09-16T00:24:04+00:00
url: /articles/windows-live-writer-tricks-and-tips.html
0:
  - f066cd3bf435c5d6fa2bf462d8281639d5db45b838d5ee37dff25566e2baa85b090f183d18a2c372c6155040c6a68a59
1:
  - 6f8a19f33b51d7677f532d956a52e05f3c46b4486c438db0dca9d40c2496f0fb31a98d6f9792cab78166c62c9a74c574
2:
  - d54da9526f91624e5559d44f360f0418151e3bd6df2c108fda8fb4c2ad05e206c6d259026bb446d7806e5a6f4e9e86cb
3:
  - 8f63b35cd3d7427ca77f1c9d1a85c56dae1fd272c919f2d722acb12096908928879cc179704b9583a70496415cc12972
4:
  - 6de715560264e4114f6d37a67bb5e02f517c57d5ce3b7506ca1060b5fc30142942212b4417cca48c12c4a0741667d8b7
5:
  - af515e83452b2dfb91a2a37d1929464fe84cc006b76152ec165dac4c57e2234d0ecb65473894897ce958fd8afd351679
6:
  - dbd36f82780decd16b09a3808f3401d7825893472c4285ceb0f110582922b0708cd4f5b9ecb14ca6524c352ede4e225d
7:
  - 5bbdb07692b97043e42b2643a8720b52c82f7a01e0ad081d3d2932949ea86afc482adc0e33242973b3645c682500a395
8:
  - ab16521370ea708abcd099c03aeb2a44497d9719ccbe429ef954ec3064bab8830eef3cc80739e4e92b8e272b948d87f4
9:
  - 32842ed5f2254d816b34a903aa25a0b8f4bb9ac269830146b1c0da392398a64732f7ac6a57fe55e3498885f6872efeb9
10:
  - fe04f5c238a275a8c3344006feb33fc931dffab53fb545c05b45a6232a40568640807cd46bb02b9a594ba593a023c64b
comment_count:
  - 11
trackback_count:
  - 1
related_posts:
  - 'a:2:{s:4:"time";i:1224876240;s:13:"related_posts";s:1480:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/backup-windows-live-writer.html" title="如何全面备份Windows Live Writer">如何全面备份Windows Live Writer</a></li><li><a href="http://www.digglife.cn/articles/windows-live-writer-tricks-and-tips-2.html" title="我的Windows Live Writer使用心得 Part.2">我的Windows Live Writer使用心得 Part.2</a></li><li><a href="http://www.digglife.cn/articles/windows-live-writer-beta2-troubleshoot.html" title="Windows Live Writer 2无法安装和资源占用过高的解决方案">Windows Live Writer 2无法安装和资源占用过高的解决方案</a></li><li><a href="http://www.digglife.cn/articles/alternative-for-windows-live-writer-juziyue.html" title="菊子曰博客离线编辑器Alpha 3 SP1评测">菊子曰博客离线编辑器Alpha 3 SP1评测</a></li><li><a href="http://www.digglife.cn/articles/clean-up-desktop-improve-productivity-2.html" title="彻底清空桌面,让启动程序更加高效Part.2">彻底清空桌面,让启动程序更加高效Part.2</a></li><li><a href="http://www.digglife.cn/articles/clean-up-desktop-improve-productivity-1.html" title="彻底清空桌面,让启动程序更加高效Part.1">彻底清空桌面,让启动程序更加高效Part.1</a></li><li><a href="http://www.digglife.cn/articles/google-apps-firefox-sidebar.html" title="集装:在Firefox侧边栏载入Google应用">集装:在Firefox侧边栏载入Google应用</a></li></ul>";}'
views:
  - 2359
bot_views:
  - 2281
duoshuo_thread_id:
  - 1154125469839261932
categories:
  - Windows技巧
tags:
  - windows live writer
  - 微软
  - 软件

---
Windows Live Writer(WLW)是我一直在使用的博客离线撰写工具,除了某些在Ubuntu下编写的日志之外,几乎所有<a title="关于DiggLife" href="https://www.digglife.net/about/" target="_blank">DiggLife</a>上的文章都是使用WLW发布的.这的确是一款值得大力推荐的博客离线撰写工具,前些天<a title="Windows Live Beta3安装和使用" href="https://www.digglife.net/articles/firstlook-of-windows-live-writer-beta3.html" target="_blank">Live团队发布了Beta 3版本</a>,你可以下载<a title="Windows Live Suite Beta所有程序的独立安装包" href="https://www.digglife.net/articles/windows-live-suite-indivisual-installers.html" target="_blank">最新版的Windows Live Writer的独立安装包</a>.下面我和大家分享一下我使用WLW的心得,希望对使用WLW发布日志的朋友有所帮助.</p> 

<!--more-->

### **一.选项设置.**

**1.Ping服务设置.**

使用Ping服务能够快速通知搜索引擎或者Feed爬虫更新你的博客.网上有很多人列出了近百个Ping地址,个人觉得没有必要加入那么多.下面是我加入的一些Ping服务器地址:

http://www.feedsky.com/api/RPC2

http://ping.feedburner.com

http://rpc.technorati.com/rpc/ping

http://blogsearch.google.com/ping/RPC2

http://www.xianguo.com/xmlrpc/ping.php

http://www.bloglines.com/ping

http://blog.iask.com/ping.php

http://so.blog.qihoo.com/pingblog.html

http://rpc.pingomatic.com/

http://api.my.yahoo.com/RPC2

http://api.my.yahoo.com/rss/ping

依次为：<a title="Feedsky" href="http://www.feedsky.com" target="_blank">Feedsky</a>,<a title="Feedburner" href="http://www.feedburner.com/" target="_blank">Feedburner</a>,<a title="Technorati" href="http://www.technorati.com" target="_blank">Technorati</a>,<a title="谷歌相关" href="https://www.digglife.net/articles/category/about-google/" target="_blank">Google</a>博客搜索,鲜果,Bloglines阅读器,新浪博客搜索,奇虎博客搜索,Pingomatic的Ping服务,雅虎阅读器.抓虾貌似还没有Ping服务.更加完整的Ping服务地址载于Feedsky客服Src的博客:<a title="博客ping服务地址完全列表" href="http://glif.cn/2006/12/ping.html" target="_blank">完美的ping通知</a>.不推荐加入太多,因为会减慢文章发布速度.

**2.自动保存和提示**

为防止意外情况发生(死机,停电等)建议勾选自动保存,时间可以自定义.勾选指定标题,添加类别和关键字提醒,以免忘记.提醒添加标签可以根据情况选择,如果没有加入社会化书签网址标签的习惯(我现在才开始使用),可以不勾选,但是另外的两个建议勾选.

[<img id="id" height="415" alt="settings" src="https://www.digglife.net/wp-content/uploads/3/379/2007/09/settings-thumb.png" width="353" />][1]

### **二.文章编辑.**

**1.关闭智能更正功能.**

当你输入链接和邮件地址的时候,WLW会自动将其更改为可点击模式,这时你可以使用**Ctrl+Z**快捷键恢复纯文本,或者可以右键点击该链接选择"删除链接".

**2.插入链接需要注意的3点.**

  * **链接词汇表.**将经常会链接到的网址添加到链接词汇表,这样以后给同样的文字添加链接的时候就不用重新输入URL了.这样的链接一般为某些大站的主页地址,朋友的博客,自己的分类链接等,长久的积累能够让你节省很多时间.如果WLW能够做到输入相关文字即可识别就更好了. 

[<img id="id" height="326" alt="links" src="https://www.digglife.net/wp-content/uploads/3/379/2007/09/links-thumb.png" width="450" />][2]

  * **链接标题.**给链接添加适当的标题是非常好的习惯,对博客的SEO有很大的好处.我之前一直忽略了这一点,现在尽量将链接都添上标题. 
  * **链接到以前的日志.**WLW开始的版本只能添加从本地发过的日志链接,不过现在能够扫描到所有在线日志.所以,如果你发现正在编辑的日志和存档日志有关联,最好设计一段话链接到之前的日志. 

**3.使用选择性粘贴.**

当你使用Ctrl+V来粘贴来富文本时,所有原本的文本格式比如字体,超链接等将会全部保留.但是有时这会让你的日志看起来很不协调,所以我们可以使用选择性粘贴模式.使用快捷键**Ctrl+Shift+V**,WLW会弹出一个对话框让你从3总粘贴方式中选择,具体保留和去除的细节对话框中有详细的说明.

[<img id="id" height="293" alt="paste-special" src="https://www.digglife.net/wp-content/uploads/3/379/2007/09/paste-special-thumb.png" width="450" />][3]

**4.图片插入.**

  * **图片大小更改.**我们手头上需要插入的图片时常会不符合博客模板,这是需要对图片进行大小上的更改.我们可以点击图片,将鼠标移动到图片边缘的小方格,通过拖动来改变大小.另外,右边栏的图片选项中也可以自定义图片大小,建议勾选锁定纵横比,不然图片会变得很难看. 
  * **保存常用的图片设置.**比如我经常使用的图片设置是:文字环绕为嵌入,边框为从博客继承,链接到原图像,宽度为450,这时我可以将其保存为默认设置,这样再次插入时即便不符合要求,也只需要更改1-2个选项即可.根据日志的不同要求更改默认设置可以大大提高图片插入效率. 
  * **关于图片效果的使用.**我不推荐插入电脑截图时使用投影和相片效果,一方面加入效果后会图片会占用更大的空间,但是WLW中显示时还是为你设置的大小,这样可能会莫名其妙地造成页面崩溃. 另外,关于图片模糊的问题,WLW在Beta 3已经有所改进,但是我们在截图时还是要注意,比如模板适应的大小是450PX宽度,尽量在截图时就截成该宽度,插入原图的话WLW不会进行压缩,这样就会很清晰.如果图片实在很大,就将图片的"链接到"选项设置为原始大小的图片,读者点击图片即可看到清晰的图像了.

非常希望WLW能够新增一个类似于链接词汇表的功能到图片板块,这样就可以直接插入曾经上传过的图片了.

**5.插入视频.**

如果你插入的是Youtube,MSN Soapbox,Google Video,只需要直接**粘贴播放地址到正文**即可,不需要点击"插入视频",WLW能够自动转换为嵌入视频.这是Beta 3的新特点.

**6.一些有用的快捷键.**

  * Ctrl+K &#8211; 插入超链接 
  * Ctrl+L &#8211; 插入图片 
  * Ctrl+S &#8211; 保存本地草稿 
  * Ctrl+N &#8211; 新建日志 
  * Ctrl+G &#8211; 新建页面 
  * F9 &#8211; 显示或隐藏侧边栏 
  * F11 &#8211; Web版式 
  * F12 &#8211; Web预览 

WLW的很多编辑功能和Office Word非常类似,可以参考一下<a title="8个你可能不知道的Word编辑技巧" href="https://www.digglife.net/articles/8-tips-of-word-you-may-not-know.html" target="_blank">8个你可能不知道的Word编辑技巧</a>.

**Part 2主要内容**:文章发布和插件推荐.

<div class="wlWriterSmartContent" id="scid:0767317B-992E-4b12-91E0-4F059A8CECA8:107df04f-5fa2-418c-8c34-28a917db09ff" style="padding-right: 0px; display: inline; padding-left: 0px; padding-bottom: 0px; margin: 0px; padding-top: 0px">
  Technorati 标签: <a href="http://technorati.com/tags/windows%20live%20writer/" rel="tag">windows live writer</a> , <a href="http://technorati.com/tags/%e6%8a%80%e5%b7%a7/" rel="tag">技巧</a> , <a href="http://technorati.com/tags/%e5%be%ae%e8%bd%af/" rel="tag">微软</a> , <a href="http://technorati.com/tags/%e8%bd%af%e4%bb%b6/" rel="tag">软件</a>
</div>

 [1]: https://www.digglife.net/wp-content/uploads/3/379/2007/09/settings.png
 [2]: https://www.digglife.net/wp-content/uploads/3/379/2007/09/links.png
 [3]: https://www.digglife.net/wp-content/uploads/3/379/2007/09/paste-special.png
