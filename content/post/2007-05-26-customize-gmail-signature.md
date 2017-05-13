---
title: Gmail技巧:让你的签名绚起来
author: 摩摩诘
type: post
date: 2007-05-26T08:26:51+00:00
url: /articles/customize-gmail-signature.html
comment_count:
  - 3
related_posts:
  - 'a:2:{s:4:"time";i:1224864664;s:13:"related_posts";s:1320:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/how-to-download-published-google-docs.html" title="如何下载公开的Google文档和电子表格">如何下载公开的Google文档和电子表格</a></li><li><a href="http://www.digglife.cn/articles/gmail7%e5%a4%a7%e6%9c%89%e5%85%b3%e9%99%84%e4%bb%b6%e7%9a%84%e6%8a%80%e5%b7%a7.html" title="Gmail:7大有关附件的技巧">Gmail:7大有关附件的技巧</a></li><li><a href="http://www.digglife.cn/articles/google-apps-firefox-sidebar.html" title="集装:在Firefox侧边栏载入Google应用">集装:在Firefox侧边栏载入Google应用</a></li><li><a href="http://www.digglife.cn/articles/top10-greasemonky-scripts-for-gmail20.html" title="10个增强Gmail新版体验的Greasemonkey代码">10个增强Gmail新版体验的Greasemonkey代码</a></li><li><a href="http://www.digglife.cn/articles/gmail-colored-lables.html" title="Gmail新增彩色标签功能">Gmail新增彩色标签功能</a></li><li><a href="http://www.digglife.cn/articles/google-reader-top-recommendations.html" title="Google Reader首页新增个性化订阅推荐">Google Reader首页新增个性化订阅推荐</a></li><li><a href="http://www.digglife.cn/articles/gmail-newer-version.html" title="Gmail新版体验">Gmail新版体验</a></li></ul>";}'
bot_views:
  - 2187
views:
  - 5402
duoshuo_thread_id:
  - 1154125469839261781
categories:
  - 火狐技巧
tags:
  - gmail
  - google
  - 个性化
  - 签名

---
尽管Gmail提供了个性签名功能,但是却并没有提供如雅虎邮箱和网易邮箱一样的富文本编辑器,在默认情况下我们只能填入纯文本式的签名,这未免太过乏味.如果使用<a href="http://www.mozilla.com/zh-CN/thunderbird/" target="_blank">Mozilla Thunderbird</a>等邮件桌面客户端的话,当然可以发送包含有Htlm代码的签名,比如超链接,图片等等.但是我从来不用类似的软件,也许很多人认为很方便,但是我一直用不习惯.所以我希望找到一种方法,能够直接在网络客户端上就让我的签名能够包含有自己博客的Logo,链接,或者自定义的邮件地址图片等等.

现在,终于能够实现我长久以来的心愿了. 效果如下:

<span style="color: #ff0080;">Gmail显示效果</span>

[<img style="border-width: 0px" src="http://digglife.qiniudn.com/wp-content/uploads/3/379/2007/05/windowslivewritergmail-e5d6signature-thumb1.png" border="0" alt="" width="440" height="293" />][1]
  
<!--more-->


  
<span style="color: #ff0080;">发给163邮箱的显示效果.</span>

[<img style="border: 0px none " src="http://digglife.qiniudn.com/wp-content/uploads/3/379/2007/05/windowslivewritergmail-e5d6signature163-thumb1.png" border="0" alt="" width="440" height="370" />][2]

### **使用方法**

**1.**给Firefox安装<a href="https://addons.mozilla.org/en-US/firefox/addon/4866" target="_blank">Better Gmail扩展</a>.这个扩展我曾经介绍过两次:<a title="Firefox:个性化Gmail(Better Gmail扩展)" href="https://www.digglife.net/articles/customize-gmail-better-gmail.html" target="_blank">Firefox:个性化Gmail(Better Gmail扩展)</a>,<a title=" 	Firefox:个性化Gmail续集(Better Gmail 0.5)" href="https://www.digglife.net/articles/customize-gmail-better-gmail05.html" target="_blank">Firefox:个性化Gmail续集(Better Gmail 0.5)</a>.不过一直关注于它带来的皮肤,搜索功能,和Google Reader的整合等,没有注意到原来它给Gmail设置里的签名设置添加了&#8221;允许HTML签名&#8221;的选项.

[<img style="border-width: 0px" src="http://digglife.qiniudn.com/wp-content/uploads/3/379/2007/05/windowslivewritergmail-e5d6signatureoptions-thumb.png" border="0" alt="" width="325" height="230" />][3]

**2.**进入Gmail设置,在签名栏目里将&#8221;Allow HTML in Signature&#8221; 勾上.

**3.**现在你就可以添加自己的HTML代码了,但是注意,有些代码Gmail并不支持.具体的支持情况可以查看[David Greiner’s A Guide to CSS Support in Email][4].

下面介绍一种简单的代码,包括图片(如博客的Favicon等)和链接.

鉴于某些邮箱有不兼容的情况,制作HTML签名的最好办法是使用Table.

> `<table style="font-size:11px;color:#555;border-collapse:collapse;"><br />
<tr><br />
<td><img src="你的图片链接" alt="531" /></td><br />
<td>....</td>`
> 
> `...(可以添加多个<td>)<br />
<td><a href="你的链接">链接标签</a></td><br />
</tr><br />
</table>`

**注意:**

  1. Style里面的具体参数你可以自定义,以达到你自己喜欢的效果.
  2. 某些邮箱客户端会屏蔽邮件中的图片,这时`<img alt=""` 中引号内部的内容会代替图片出现.
  3. 弊端:你必须在安装有Better Gmail扩展的Firefox中发送才有效,不然签名只会显示为一段没有丝毫意义的HTML代码.

[<img style="border-width: 0px" src="http://digglife.qiniudn.com/wp-content/uploads/3/379/2007/05/windowslivewritergmail-e5d6signaureerror-thumb1.png" border="0" alt="" width="450" height="238" />][5]

当然,你可以使用更多的HTML代码.但是记住不要使用太多,一来可能会被屏蔽,二来你的收件人也可能会很反感.

翻译改写自:<a href="http://5thirtyone.com/archives/821" target="_blank">5thirtyone</a>

 [1]: https://www.digglife.net/wp-content/uploads/3/379/2007/05/windowslivewritergmail-e5d6signature3.png
 [2]: https://www.digglife.net/wp-content/uploads/3/379/2007/05/windowslivewritergmail-e5d6signature1635.png
 [3]: https://www.digglife.net/wp-content/uploads/3/379/2007/05/windowslivewritergmail-e5d6signatureoptions2.png
 [4]: http://www.campaignmonitor.com/blog/archives/2006/03/a_guide_to_css_support_in_emai.html
 [5]: https://www.digglife.net/wp-content/uploads/3/379/2007/05/windowslivewritergmail-e5d6signaureerror3.png