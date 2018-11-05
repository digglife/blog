---
title: 如何制作纯 ASCII 文本流程图
author: 摩摩诘
type: post
date: 2015-03-27T15:48:06+00:00
excerpt: 在 StackOverflow 上经常看到有人为了说明程序实现或者服务架构而插入一个纯 ASCII 文本的流程图。相比图片式的流程图，纯 ASCII 文本的流程图简洁明了，插入方便，节省空间，便于移植，用来说明技术问题的效果非常好。
url: /articles/ascii-flowchart-how-to.html
index_image:
  - https://www.digglife.net/wp-content/uploads/2016/05/flowchart-how-to.png
views:
  - 1453
duoshuo_thread_id:
  - 1154125469839262204
post_views_count:
  - 3
categories:
  - 代码卷轴
tags:
  - ASCII
  - perl
  - puppet
  - 流程图

---
在 StackOverflow 上经常看到有人为了说明 程序实现 或者 服务架构 而插入一个纯 ASCII 文本的流程图。相比图片式的流程图， <a href=" https://www.digglife.net/articles/ascii-flowchart-how-to.html" title="如何制作纯 ASCII 文本的流程图" target="_blank">ASCII 文本流程图</a>简洁明了，插入灵活，节省空间，便于移植，用来说明技术问题刚刚好。

<!--more-->

<img src="https://www.digglife.net/wp-content/uploads/2016/05/graph-easy-flowchart.png" alt="Graph::Easy生成ASCII流程图" width="500" height="273" />

总的来说，制作这种 ASCII 文本的流程图有两个方式：

  1. 使用所见即所得的流程图制作工具
  2. 手写代码生成 ASCII 流程图

前者制作起来直观，可以发挥想象力制作各种 ASCII Art，但是其实质和图片式的流程图制作没有两样，需要用鼠标手动调整布局。后者不够直观，但是因为能用指令直接生成布局，如果熟悉代码语法的话制作起来要快很多，而且通常来说更加精准。

### 所见即所得的 ASCII 流程图制作工具

  1. **ASCIIO**
<a href="http://search.cpan.org/dist/App-Asciio/lib/App/Asciio.pm" title="Perl模块 Asciio" target="_blank">ASCIIO</a> 是一个 [Perl][1] 编写的 GTK 程序，操作直观。除了一些流程图基本要素之外，ASCIIO 还内置一些经常会用到的ASCII图像，比如用户终端，服务器，交换机，数据库，防火墙等等。

  2. **ASCIIFlow Infinity**
<a href="http://asciiflow.com/" title="ASCII流程图在线编辑器 ASCIIFlow" target="_blank">ASCIIFlow</a> 是一个知名的在线ASCII流程图制作工具。编辑工具比较简单，但是基本够用，支持和 Google Drive 连接，方便保存和分享。

除了以上这两个之外，其实VIM也有两个比较知名的插件，<a href="http://www.vim.org/scripts/script.php?script_id=40" title="VIM插件 DrawIt" target="_blank">Drawit!</a>和 <a href="http://www.vim.org/scripts/script.php?script_id=705" title="VIM插件Sketch" target="_blank">Sketch</a> ，纯键盘操作，适合骨灰 VIM 党。

### 手写代码生成 ASCII 流程图

**Graph::Easy**

<a href="http://search.cpan.org/~tels/Graph-Easy/lib/Graph/Easy.pm" title="ASCII流程图制作模块 Graph::Easy" target="_blank">Graph::Easy</a> 看名字就知道是一个 Perl 模块。除了可以通过写 Perl 代码来生成 ASCII 流程图之外，通过这个模块附带的一个可执行文件 `graph-easy` 可以将写好的文本指令转换成 ASCII 流程图。 当然，所谓可执行文件其实就是一个带参数控制的 Perl 脚本。

<a href="http://www.bloodgate.com/perl/graph/manual/index.html" title="Graph::Easy 帮助手册" target="_blank">Graph::Easy 的语法</a>也比较简单，符合直觉，比如我随手写的一个 简单的 Puppet 架构图：

<pre lang='text'>[ Puppet Agents ]{rows:2} ~~ facts ~~> [ Puppet Master ]{rows:4} ~~ factsn catalogs ~~> [ PuppetDB ]{flow:south} -- REST API --> [ Developers ]
[ Puppet Master ] -- policies --> [ Puppet Agents ]
[ Developers ] -- modules --> [ Puppet Master ]
(Backends : [ PuppetDB ] -- data --> [ PostgreSQL ])
[ PostgreSQL ] -- data --> [ PuppetDB ]
</pre>

`graph-easy` 命令解析以上文本会生成下面这样的 ASCII 流程图：

<pre lang='text'>+ - - - - - - - - - - - - - - - - - - - +
                                                            ' Backends :                            '
                                                            '                                       '
                                                            '                data                   '
                                                            '   +----------------------+            '
                                                            '   v                      |            '
+---------------+             +---------------+  facts      ' +------------+         +------------+ '
|               |  facts      |               |  catalogs   ' |  PuppetDB  |  data   | PostgreSQL | '
|               | ~~~~~~~~~~> |               | ~~~~~~~~~~> ' |            | ------> |            | '
|               |             |               |             ' +------------+         +------------+ '
| Puppet Agents |             |               |             '                                       '
|               |             | Puppet Master |             + - - - - - - - - - - - - - - - - - - - +
|               |  policies   |               |                 |
|               | &lt;---------- |               |                 | REST API
+---------------+             |               |                 v
                              |               |  modules      +------------+
                              |               | &lt;----------   | Developers |
                              +---------------+               +------------+

</pre>

除了生成 ASCII 文本的流程图之外，Graph::Easy 还支持输出为 HTML，SVG，GDL，GraphML 等等，结合<a href="http://graphviz.org" title="Graphviz" target="_blank">dot（graphviz）</a>还支持常见图片输出。如果希望输出的流程图更漂亮，还可以利用 Graph::Easy 提供的各种自定义属性，语法类似css，当然这些对于默认的 ASCII 文本输出没有什么作用。

注：dot（graphviz）在 OS X 上可以通过`brew install graphviz`命令安装。

对 Graph::Easy 提供的语法熟悉之后，生成 ASCII 流程图肯定是比使用所见即所得的编辑器更快的，而且布局更整洁精准，这种方式也更加符合程序员的思维。

 [1]: https://www.digglife.net/articles/tag/perl "Perl 相关文章"
