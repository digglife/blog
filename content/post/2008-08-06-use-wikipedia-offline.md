---
title: 离线搜索维基百科WikiTaxi
author: 摩摩诘
type: post
date: 2008-08-06T02:06:02+00:00
url: /articles/use-wikipedia-offline.html
related_posts:
  - 'a:2:{s:4:"time";i:1224885084;s:13:"related_posts";s:1323:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/knol-open.html" title="Google的维基百科Knol正式开放">Google的维基百科Knol正式开放</a></li><li><a href="http://www.digglife.cn/articles/my-favorite-vista-features.html" title="我最喜欢的Windows Vista功能">我最喜欢的Windows Vista功能</a></li><li><a href="http://www.digglife.cn/articles/picture-textaizer-ascii-art.html" title="将普通图片转换为字符或ASCII码拼图">将普通图片转换为字符或ASCII码拼图</a></li><li><a href="http://www.digglife.cn/articles/ubuntu-windows-xp-vista-firefox-profile.html" title="Ubuntu,Windows Vista和XP共享Firefox配置文件">Ubuntu,Windows Vista和XP共享Firefox配置文件</a></li><li><a href="http://www.digglife.cn/articles/custom-windows-interface-tools.html" title="9个工具打造焕然一新的Windows界面">9个工具打造焕然一新的Windows界面</a></li><li><a href="http://www.digglife.cn/articles/convert-powerpoint-flash.html" title="免费将Powerpoint转换为Flash">免费将Powerpoint转换为Flash</a></li><li><a href="http://www.digglife.cn/articles/alternative-for-windows-live-writer-juziyue.html" title="菊子曰博客离线编辑器Alpha 3 SP1评测">菊子曰博客离线编辑器Alpha 3 SP1评测</a></li></ul>";}'
views:
  - 17900
bot_views:
  - 4686
syntaxhighlighter_encoded:
  - 1
duoshuo_thread_id:
  - 1154125469839262105
categories:
  - 酷软推荐
tags:
  - 维基百科
  - 词典
  - 软件

---
维基百科有海量的资料供我们查询，如果我们能够将维基百科保存到本地磁盘，实现离线查询，能够大大节约时间，同时还能装进U盘随身携带，对于经常需要查询资料的朋友来说是个非常不错的选择。写英文论文或者仅仅是学习英文，维基百科都会是一个好帮手。

<a title="离线搜索维基百科WikiTaxi" href="https://www.digglife.net/articles/use-wikipedia-offline.html" target="_blank">便携软件WikiTaxi</a>能够让你离线阅读和搜索各种语言的维基百科，所有的维基资料都会存储在WikiTaxi的数据库里面，无需网络连接。网上已经有包括中文维基在内的各种语言版本的维基离线文件，间隔几周就会更新一次，如果你想更新本地维基数据库，可以从网上下载最新版本。

<!--more-->

下面介绍WikiTaxi的使用方法：

1、到<a title="WikiTaxi主页" href="http://wikitaxi.org/delphi/doku.php/products/wikitaxi/index" target="_blank">WikiTaxi主页</a>下载WikiTaxi主文件，无需安装，解压之后即可使用。

2、<a title="维基百科离线文件下载" href="http://wikitaxi.org/delphi/doku.php/products/wikitaxi/index#download_the_wiki_backup" target="_blank">下载维基百科离线文件</a>，导入到WikiTaxi的数据库中，视乎文件的大小导入时间长短不一，当然，这样的操作是一次性的。如果你想试用一下先，推荐先下载[简化版英文维基百科][1]。这里需要注意的是，一般我们要进入有最新版本的Latest目录下，并下载文件名含有`pages-articles.xml.bz2`的压缩包。

<div style="width: 410px" class="wp-caption aligncenter">
  <img title="WikiTaxi导入维基离线文件" src="https://www.digglife.net/wp-content/uploads/archive/winkitaxi-import.jpg" alt="导入33MB的维基文件大概需要30秒左右的时间" width="400" height="275" />
  
  <p class="wp-caption-text">
    导入33MB的维基文件大概需要30秒左右的时间
  </p>
</div>

3、打开刚才创建的.taxi数据库就可以开始离线查询维基百科了。

<div style="width: 410px" class="wp-caption aligncenter">
  <img title="WikiTaxi查询离线维基百科" src="https://www.digglife.net/wp-content/uploads/2008/08/wikitaxi-search-browse.gif" alt="离线文件查询得自然很快,而且排版也和网络版维基百科相差无几" width="400" height="338" />
  
  <p class="wp-caption-text">
    离线文件查询得自然很快,而且排版也和网络版维基百科相差无几
  </p>
</div>

<div style="width: 410px" class="wp-caption aligncenter">
  <img title="WikiTaxi查询中文版离线维基百科" src="https://www.digglife.net/wp-content/uploads/2008/08/wikitaxi-chinese.gif" alt="WikiTaxi查询中文版离线维基百科" width="400" height="338" />
  
  <p class="wp-caption-text">
    查询中文维基也完全没有问题
  </p>
</div>

4、如果你经常访问某个数据库，可以创建一个快捷方式，并设置其目标为如下模式：

`"%路径%\WikiTaxi.exe" "%路径%\ensimple.taxi"`

比如:_&#8220;D:\Program Files\WikiTaxi\WikiTaxi.exe&#8221; &#8220;D:\Program Files\WikiTaxi\ensimple.taxi&#8221;_

据我测试这个简化版英文维基来看，这个离线解决方案还是非常完美的，完整版本的英文维基文件有3.9GB，想必内容要比这个简化版好很多，强烈推荐经常查询维基的朋友下载。这玩意当字典用都可以，读维基的解释要比看传统的字典爽多啦。中文版的我只找到一个100多MB的版本，估计内容很不完整。

<a title="WikiTaxi主页" href="http://www.wikitaxi.org/delphi/doku.php/products/wikitaxi/index" target="_blank">WikiTaxi主页</a>

<a title="完整英文版维基百科离线文件下载" href="http://dumps.wikimedia.org/enwiki/latest/" target="_blank">完整英文版维基百科离线文件下载</a>

<span style="color: #ff0000;">更新</span>:前天开始有朋友反映WikiTaxi无法访问，后来发现我也不能上了，不知道是不是功夫网的杰作，我将WikiTaxi的压缩包上传到纳米盘了(发现Fs2you也无法访问了)，如果连纳米盘都无法打开，可以让我直接E给你。

[WikiTaxi 1.0.3下载][2]

 [1]: http://dumps.wikimedia.org/simplewiki/latest/simplewiki-latest-pages-articles.xml.bz2 "简化版英文维基百科下载"
 [2]: http://www.namipan.com/d/644ac5b191c5803d62be48fb6a32175b6618632892e40e00
