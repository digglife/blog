---
title: 如何更改 OS X 的系统默认中文字体
author: 摩摩诘
type: post
date: 2014-08-10T17:30:22+00:00
excerpt: OS X 从 Jaguar 开始就将华文黑体作为系统默认的简体中文字体，但其实从 Snow Leopard 开始引入的冬青黑体在整体显示效果更胜一筹，我们可以通过修改系统配置文件的方式更改 OS X 的系统默认中文字体为冬青黑体。
url: /articles/change-system-default-font-osx.html
index_image:
  - https://www.digglife.net/wp-content/uploads/2014/08/osx-font.png
views:
  - 1224
duoshuo_thread_id:
  - 1154125469839262187
wp-syntax-cache-content:
  - |
    a:1:{i:1;s:1177:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="line_numbers"><pre>1
    2
    3
    </pre></td><td class="code"><pre class="css" style="font-family:monospace;">body <span style="color: #00AA00;">&#123;</span>
    <span style="color: #000000; font-weight: bold;">font</span><span style="color: #00AA00;">:</span> <span style="color: #933;">20px</span>/<span style="color: #933;">24px</span> <span style="color: #ff0000;">&quot;Lucida Grande&quot;</span><span style="color: #00AA00;">,</span> <span style="color: #ff0000;">&quot;Hiragino Sans GB&quot;</span><span style="color: #00AA00;">,</span> <span style="color: #ff0000;">&quot;Microsoft Yahei&quot;</span><span style="color: #00AA00;">,</span> <span style="color: #ff0000;">&quot;WenQuanYi Micro Hei&quot;</span><span style="color: #00AA00;">,</span> <span style="color: #993333;">sans-serif</span><span style="color: #00AA00;">;</span>
    <span style="color: #00AA00;">&#125;</span></pre></td></tr></table><p class="theCode" style="display:none;">body {
    font: 20px/24px &quot;Lucida Grande&quot;, &quot;Hiragino Sans GB&quot;, &quot;Microsoft Yahei&quot;, &quot;WenQuanYi Micro Hei&quot;, sans-serif;
    }</p></div>
    ";}
categories:
  - Mac学习
tags:
  - mac
  - OSX
  - 字体

---
[OS X][1] 从 Jaguar（OS X 10.2）就将华文黑体作为系统默认的简体中文字体，但其实从 Snow Leopard 开始引入的冬青黑体在整体显示效果上更胜一筹，我们可以通过修改系统配置文件的方式[更改 OS X 的系统默认中文字体为冬青黑体][2]。

冬青黑体可能能有些字型在笔画风格上和我们的习惯有所差别，但是除开这一点各方面都比华文黑体更讨好眼睛，所以我刚开始把 [Firefox][3] 的简体中文字体替换成了冬青黑体，今天直接把系统字体也替换了。
  
<!--more-->

步骤很简单，只需替换两个系统文件中的所有华文黑体的部分。这两个文件都在 `/System/Library/Frameworks/ApplicationServices.framework/Frameworks/CoreText.framework/Resources` 目录下，分别是 `CTPresetFallbacks.plist` 和  `DefaultFontFallbacks.plist` 。

  1. 将这两个文件复制到自己的用户目录下
比如复制到 Downloads 目录，最好还备份一份。做这一步是因为 System 目录下的文件和文件夹都只有root可写，为了省去手动修改权限的麻烦，复制出来修改然后再丢回去比较简单点。

  2. 使用 TextWrangler 打开进行编辑
这两个文件是二进制的 plist，所以普通的文本编辑器，比如 vi、Sublime 之类的无法识别，而 Mac 下的<a href="https://itunes.apple.com/us/app/textwrangler/id404010395?mt=12" title="OS X 下的免费文本编辑器 TextWrangler" target="_blank">免费编辑器 TextWrangler</a> 可以正常编辑（当然 XCode 也可以）。

  * 替换 `DefaultFontFallbacks.plist` 和 `CTPresetFallbacks.plist` 中所有的 `STHeitiSC-Light` 为 `HiraginoSansGB-W3` 。
<img src="https://www.digglife.net/wp-content/uploads/2014/08/osx-change-font.png" alt="OSX替换系统中文字体为冬青黑体" width="500" height="167" class="alignnone size-full wp-image-3844" />

  * 替换 `CTPresetFallbacks.plist` 中的 `STHeitiSC-Medium` 为 `HiraginoSansGB-W6`。
其中第一步更改的是常规体，第二步则是粗体。

  3. 将更改后的文件替换原文件
系统会提示输入密码以提升权限。替换完成之后重启系统即可生效。

可能因为冬青黑体是日本的字游工房制作的原因，日文显示也非常棒，所以替换之后[中日混排][4]的效果也远远比之前的漂亮，可以看下图中假名，华文黑体的假名完全不能看。

<img src="https://www.digglife.net/wp-content/uploads/2014/08/zh-ja-text-500x312.png" alt="冬青黑体华文黑体中日混排的比较" width="500" height="312" class="alignnone size-medium wp-image-3849" />

其实通过相同的步骤也可以将系统的默认西文字体更改为和 Yosemite 一样的 Helvetica Neue ，只是我实在不喜欢这个字体，还是 Lucida Grande 看着更舒服。

另，我几个月前在博客的模板中加入了针对各个平台的 Sans-Serif 字体，这样可以确保网页在各个平台上能够有相对一致的效果。今天把文章正文字号加大到16px，稍微增大了行距，并加了 `-moz-osx-font-smoothing` 属性以优化 OS X 的字体在 Firefox 下的渲染效果，比之前看着更舒服点。

<pre lang='css' line="1">body {
font: 20px/24px "Lucida Grande", "Hiragino Sans GB", "Microsoft Yahei", "WenQuanYi Micro Hei", sans-serif;
}
</pre>

 [1]: https://www.digglife.net/articles/category/mac-osx "OS X 相关文章"
 [2]: https://www.digglife.net/articles/change-system-default-font-osx.html "如何更改 OS X 的系统默认中文字体"
 [3]: https://www.digglife.net/articles/category/firefox "Firefox 相关文章"
 [4]: https://www.digglife.net/articles/japanese-font-firefox.html "完美解决Firefox下日文字体显示为宋体的问题"
