---
title: 一键显示或隐藏文件
author: 摩摩诘
type: post
date: 2008-07-28T03:52:04+00:00
url: /articles/hide-show-file-shortcut.html
related_posts:
  - 'a:2:{s:4:"time";i:1224870225;s:13:"related_posts";s:1391:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/vista-theme-visual-style-download.html" title="7个漂亮的Vista主题(视觉样式)下载">7个漂亮的Vista主题(视觉样式)下载</a></li><li><a href="http://www.digglife.cn/articles/windows-vista-sp1-download.html" title="Windows Vista SP1简体中文独立安装包官方下载">Windows Vista SP1简体中文独立安装包官方下载</a></li><li><a href="http://www.digglife.cn/articles/vista%e4%bd%bf%e7%94%a8tweakvi%e4%bc%98%e5%8c%96windows-vista.html" title="Vista:使用TweakVI优化Windows Vista">Vista:使用TweakVI优化Windows Vista</a></li><li><a href="http://www.digglife.cn/articles/active-boot-image-vista.html" title="激活Windows Vista的隐藏启动画面">激活Windows Vista的隐藏启动画面</a></li><li><a href="http://www.digglife.cn/articles/my-favorite-vista-features.html" title="我最喜欢的Windows Vista功能">我最喜欢的Windows Vista功能</a></li><li><a href="http://www.digglife.cn/articles/ubuntu-windows-xp-vista-firefox-profile.html" title="Ubuntu,Windows Vista和XP共享Firefox配置文件">Ubuntu,Windows Vista和XP共享Firefox配置文件</a></li><li><a href="http://www.digglife.cn/articles/custom-windows-interface-tools.html" title="9个工具打造焕然一新的Windows界面">9个工具打造焕然一新的Windows界面</a></li></ul>";}'
bot_views:
  - 2496
views:
  - 8633
syntaxhighlighter_encoded:
  - 1
duoshuo_thread_id:
  - 1154125469839262171
wp-syntax-cache-content:
  - |
    a:1:{i:1;s:1965:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="line_numbers"><pre>1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    </pre></td><td class="code"><pre class="vb" style="font-family:monospace;"><span style="color: #151B8D; font-weight: bold;">Set</span> sh = <span style="color: #E56717; font-weight: bold;">CreateObject</span>(“WScript.Shell“)
    theKey = “HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced\Hidden“
    setHidden = sh.RegRead(theKey)
    <span style="color: #8D38C9; font-weight: bold;">If</span> setHidden = 1 <span style="color: #8D38C9; font-weight: bold;">Then</span>
    setHidden = 0
    MsgBox “System <span style="color: #8D38C9; font-weight: bold;">and</span> hidden files will no longer appear <span style="color: #8D38C9; font-weight: bold;">in</span> Explorer.“,64,“Hidden File Exchange“
    <span style="color: #8D38C9; font-weight: bold;">Else</span>
    setHidden = 1
    MsgBox “System <span style="color: #8D38C9; font-weight: bold;">and</span> hidden files will appear <span style="color: #8D38C9; font-weight: bold;">in</span> Explorer.“,64,“Hidden File Exchange“
    <span style="color: #8D38C9; font-weight: bold;">End</span> <span style="color: #8D38C9; font-weight: bold;">If</span>
    sh.RegWrite theKey,setHidden,“REG_DWORD“
    <span style="color: #151B8D; font-weight: bold;">Set</span> sh = <span style="color: #00C2FF; font-weight: bold;">Nothing</span></pre></td></tr></table><p class="theCode" style="display:none;">Set sh = CreateObject(“WScript.Shell“)
    theKey = “HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced\Hidden“
    setHidden = sh.RegRead(theKey)
    If setHidden = 1 Then
    setHidden = 0
    MsgBox “System and hidden files will no longer appear in Explorer.“,64,“Hidden File Exchange“
    Else
    setHidden = 1
    MsgBox “System and hidden files will appear in Explorer.“,64,“Hidden File Exchange“
    End If
    sh.RegWrite theKey,setHidden,“REG_DWORD“
    Set sh = Nothing</p></div>
    ";}
categories:
  - Windows技巧
tags:
  - vista
  - windows
  - windows技巧

---
在[Windows][1]下我们经常要查看或者编辑某些隐藏文件，比如系统盘的Boot.ini，Appdata中的Firefox配置文件等等，通常情况下我们的做法是在文件夹选项里面进行设置，但是每次都要这样进行显示/隐藏的操作未免麻烦。

所以就有了这个显示隐藏文件的快捷键，创建方法非常简单，只需进行复制粘贴操作即可。这段代码是通过对注册表的编辑实现隐藏和显示文件功能的。

<!--more-->

1.打开记事本，输入以下代码：

<pre lang="vb" line="1">Set sh = CreateObject(“WScript.Shell“)
theKey = “HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced\Hidden“
setHidden = sh.RegRead(theKey)
If setHidden = 1 Then
setHidden = 0
MsgBox “System and hidden files will no longer appear in Explorer.“,64,“Hidden File Exchange“
Else
setHidden = 1
MsgBox “System and hidden files will appear in Explorer.“,64,“Hidden File Exchange“
End If
sh.RegWrite theKey,setHidden,“REG_DWORD“
Set sh = Nothing</pre>

2.将文件另存为.vbs结尾的文件

3.双击即可生效。注意在[Vista][2]下UAC必须在关闭状态才能使用。

[![显示隐藏文件][3]][4]

4.如果你不想看到上面这样的隐藏或显示提示对话框,可以直接删除以Msgbox开头的第6行和第9行。

来自[CyberNet][5]

PS：前几天在注册了一个Google app，现在DiggLife也有@digglife.cn后缀的[专属Gmail邮箱][6]了，感觉不错。我本来以为cn域名想用GApp需要先用.com注册一个后再添加别名，但是发现也不用这么麻烦，只需将域名后缀写成[大写的CN][7]就可以了，另外还要背叛中国国籍，其他步骤一样，我还真是火星啊！我的新邮箱是i#digglife.cn，以后可能会经常使用，欢迎骚扰~

 [1]: https://www.digglife.net/articles/category/windows-tricks "Windows技巧"
 [2]: https://www.digglife.net/articles/tag/vista "Vista相关文章"
 [3]: https://www.digglife.net/wp-content/uploads/archive/msgbox.png
 [4]: http://picasaweb.google.com/digglifeshow/oCzYfC/photo#5227898259155235714
 [5]: http://cybernetnews.com/2008/07/24/cybernotes-shortcut-to-showhide-hidden-files/
 [6]: https://www.google.com/a/digglife.cn/ "DiggLife的Google APP"
 [7]: http://zhiqiang.org/blog/posts/guide-for-google-apps.html
