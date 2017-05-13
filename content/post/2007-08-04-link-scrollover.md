---
title: 技巧:给链接文字添加滚动变化效果
author: 摩摩诘
type: post
date: 2007-08-04T02:14:12+00:00
url: /articles/link-scrollover.html
0:
  - 979142ac15d335546389dbeb830441388d214c7fd5fe67963667d5f40d39332cc950524928d80701f82517b1dbc79219
  - 979142ac15d335546389dbeb830441388d214c7fd5fe67963667d5f40d39332cc950524928d80701f82517b1dbc79219
1:
  - 097a5166e05189b48da834d91a0df7a0ad4db2bbd438a92961ee3078a250bb49b97a8b610e8af42f5596711bed80ac5b
  - 097a5166e05189b48da834d91a0df7a0ad4db2bbd438a92961ee3078a250bb49b97a8b610e8af42f5596711bed80ac5b
2:
  - a752c426b902ca5217c45871e3dffd32661b270532c04088b690ccaba57895fc3ac4a81fc9b1b9aa437b145052784f81
  - a752c426b902ca5217c45871e3dffd32661b270532c04088b690ccaba57895fc3ac4a81fc9b1b9aa437b145052784f81
3:
  - 0d5d2f2aa64c1c0a6b200fde5f00e594993eb06a602c80319888a91596dd60ba2a372da330750720a7ba6c5550cb1543
  - 0d5d2f2aa64c1c0a6b200fde5f00e594993eb06a602c80319888a91596dd60ba2a372da330750720a7ba6c5550cb1543
4:
  - 324202218dbe27a6ebf84df62bf1e94e726af95fffdeeac73e78f251fac707ea3836571685456d83f539de83b2787852
  - 324202218dbe27a6ebf84df62bf1e94e726af95fffdeeac73e78f251fac707ea3836571685456d83f539de83b2787852
5:
  - 282b7fdd4013853760dfb6c72335f66473f7e72a8ef9d964a8c5237cf3fee98b65264aa2f61156023e4a9d1b1d9ab2ea
  - 282b7fdd4013853760dfb6c72335f66473f7e72a8ef9d964a8c5237cf3fee98b65264aa2f61156023e4a9d1b1d9ab2ea
comment_count:
  - 6
related_posts:
  - 'a:2:{s:4:"time";i:1224756359;s:13:"related_posts";s:1440:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/install-compiz-fusion-and-trouble-shooting-part2-2.html" title="Ubuntu Compiz Fusion安装和常见问题解决 Part.2">Ubuntu Compiz Fusion安装和常见问题解决 Part.2</a></li><li><a href="http://www.digglife.cn/articles/install-compiz-fusion-and-trouble-shooting-part1-2.html" title="Ubuntu Compiz Fusion安装和常见问题解决 Part.1">Ubuntu Compiz Fusion安装和常见问题解决 Part.1</a></li><li><a href="http://www.digglife.cn/articles/customize-gmail-signature.html" title="Gmail技巧:让你的签名绚起来">Gmail技巧:让你的签名绚起来</a></li><li><a href="http://www.digglife.cn/articles/custom-windows-interface-tools.html" title="9个工具打造焕然一新的Windows界面">9个工具打造焕然一新的Windows界面</a></li><li><a href="http://www.digglife.cn/articles/add-compiz-fusion-stackswitch.html" title="Compiz Fusion新特效Stackswitch">Compiz Fusion新特效Stackswitch</a></li><li><a href="http://www.digglife.cn/articles/can-not-modify-category-slug.html" title="Wordpress无法编辑分类缩略名(Slug)的解决">Wordpress无法编辑分类缩略名(Slug)的解决</a></li><li><a href="http://www.digglife.cn/articles/clean-up-desktop-improve-productivity-2.html" title="彻底清空桌面,让启动程序更加高效Part.2">彻底清空桌面,让启动程序更加高效Part.2</a></li></ul>";}'
bot_views:
  - 1504
views:
  - 677
duoshuo_thread_id:
  - 1154125469839261873
categories:
  - 博客研究
tags:
  - 个性化
  - 代码
  - 特效
  - 链接

---
[<img src="http://digglife.qiniudn.com/wp-content/uploads/3/379/2007/08/scrollover21.gif" alt="scrollover21.gif" align="right" />][1]为了让大家明白这是一个怎样的效果,首先给个例子:<a href="https://www.digglife.net" class="scrollover" target="_blank" type="scrollover">DiggLife</a>.鼠标悬停到前面的链接,看看有什么变化.<strike>如果你用RSS阅读器是无法看到效果的,所以阅读器里的标题给我增加点点击率吧</strike>.(添加了GIF图片,应该能够看到)

这个效果就叫做<a href="http://www.scrollovers.com/" class="scrollover" target="_blank" type="scrollover">Scrollover</a>.下面介绍一下**实现方法**.

<!--more-->

1.复制以下一段Js代码到你的页面,或者你可以直接下载<a href="http://www.scrollovers.com/js/scrollovers.js" target="_blank">这段JS代码</a>并上传到你的网站.

> <script type=&#8221;text/javascript&#8221; src=&#8221;http://www.scrollovers.com/js/scrollovers.js&#8221;></script>

2.复制以下一段样式代码到你的CSS代码或者页面里.其中颜色可以任意改变.

> <style>
  
> a.scrollover {
  
> /\* Default Colour/Styles here \*/
  
> color: #3366CC;
  
> }
  
> a.scrollover em:first-line {
  
> /\* Rollover Colour/Styles here \*/
  
> color: #FF5A00;
  
> }
  
> </style>

3.做完这些就可以使用下面的代码实现链接滚动效果了.

> <a href=&#8221;你的链接&#8221; class=&#8221;scrollover&#8221; type=&#8221;scrollover&#8221;>链接文字</a>

注:

如果你使用的上传JS代码的方式,还可以将它更加**个性化**一点.

> <div align="left">
>   <pre>var scrollovers_TypeName = 'scrollover';
var scrollovers_StartScrollLocation = 0;
var scrollovers_EndScrollLocationTrim = 0;
var scrollovers_ScrollSpeed = 3;
var scrollovers_ScrollDownOnMouseOver = true;</pre>
> </div>
> 
> <div align="left">
>   <pre></pre>
> </div>

<p align="left">
  上面是该JS代码的开头部分.
</p>

<p align="left">
  1.如果你希望对所有链接都使用滚动效果,而不用每次都添加样式参数,可以将第一行的scrollovers_TypeName参数设置为空字符窜,也就是将引号内的scrollover去掉.
</p>

<p align="left">
  2.如果你希望滚动由下至上,可以把scrollovers_ScrollDownOnMouseOver设置为false.
</p>

<p align="left">
  3.通过更改scrollovers_ScrollSpeed的数值可以更改滚动速度.
</p>

<p align="left">
  4.如果想更改激活滚动的范围,可以定义scrollover_Nudge,如:
</p>

> <p align="left">
>   &nbsp;
> </p>
> 
> a.scrollover .scrollover_Nudge {
  
> top:-1px;
  
> }

**兼容浏览器:**

  * Firefox 2.0
  * Internet Explorer 7
  * Internet Explorer 6
  * Internet Explorer 5.5
  * Safari 3 <small>(Windows)</small>
  * Opera 9

<p align="left">
  &nbsp;
</p>

 [1]: https://www.digglife.net/wp-content/uploads/3/379/2007/08/scrollover21.gif "scrollover21.gif"