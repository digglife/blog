---
title: Perl输出数据为纯文本表格Text::ASCIITable
author: 摩摩诘
type: post
date: 2014-02-26T17:06:11+00:00
excerpt: Text::ASCIITable 是一个用来将数据以纯文本格式的表格形式输出的 Perl 模块，表格样式简洁明了，而且可以灵活地自定义，非常适合命令行程序。
url: /articles/output-data-to-fomatted-table.html
index_image:
  - https://www.digglife.net/wp-content/uploads/2014/02/perl-text-table.png
views:
  - 570
duoshuo_thread_id:
  - 1154125469839262178
wp-syntax-cache-content:
  - |
    a:1:{i:1;s:4553:"
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
    13
    14
    15
    16
    17
    </pre></td><td class="code"><pre class="perl" style="font-family:monospace;"><span style="color: #000000; font-weight: bold;">use</span> strict<span style="color: #339933;">;</span>
    <span style="color: #000000; font-weight: bold;">use</span> warnings<span style="color: #339933;">;</span>
    <span style="color: #000000; font-weight: bold;">use</span> Text<span style="color: #339933;">::</span><span style="color: #006600;">ASCIITable</span><span style="color: #339933;">;</span>
    &nbsp;
    <span style="color: #b1b100;">my</span> <span style="color: #0000ff;">@attrs</span> <span style="color: #339933;">=</span> <span style="color: #009966; font-style: italic;">qw/NAME AUTHOR BIRTH VERSION WEBSITE/</span><span style="color: #339933;">;</span>
    &nbsp;
    <span style="color: #b1b100;">my</span> <span style="color: #0000ff;">@langs</span> <span style="color: #339933;">=</span> 
    <span style="color: #009900;">&#40;</span>
        <span style="color: #009900;">&#91;</span><span style="color: #ff0000;">'Perl'</span><span style="color: #339933;">,</span><span style="color: #ff0000;">'Larry Wall'</span><span style="color: #339933;">,</span><span style="color: #ff0000;">'1987'</span><span style="color: #339933;">,</span><span style="color: #ff0000;">'5.18.2'</span><span style="color: #339933;">,</span><span style="color: #ff0000;">'http://www.perl.org'</span><span style="color: #009900;">&#93;</span><span style="color: #339933;">,</span>
        <span style="color: #009900;">&#91;</span><span style="color: #ff0000;">'Python'</span><span style="color: #339933;">,</span><span style="color: #ff0000;">'Guido Van Rossum'</span><span style="color: #339933;">,</span><span style="color: #ff0000;">'1991'</span><span style="color: #339933;">,</span><span style="color: #ff0000;">'2.7.6'</span><span style="color: #339933;">,</span><span style="color: #ff0000;">'http://www.python.org'</span><span style="color: #009900;">&#93;</span><span style="color: #339933;">,</span>
    <span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    &nbsp;
    <span style="display:block;background-color: #ffc;"><span style="color: #b1b100;">my</span> <span style="color: #0000ff;">$t</span> <span style="color: #339933;">=</span> Text<span style="color: #339933;">::</span><span style="color: #006600;">ASCIITable</span><span style="color: #339933;">-&gt;</span><span style="color: #000000; font-weight: bold;">new</span><span style="color: #009900;">&#40;</span><span style="color: #009900;">&#123;</span> headingText <span style="color: #339933;">=&gt;</span> <span style="color: #ff0000;">'Program Languages'</span><span style="color: #339933;">,</span> drawRowLine <span style="color: #339933;">=&gt;</span> <span style="color: #cc66cc;">1</span> <span style="color: #009900;">&#125;</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span></span><span style="display:block;background-color: #ffc;"><span style="color: #0000ff;">$t</span><span style="color: #339933;">-&gt;</span><span style="color: #006600;">setCols</span><span style="color: #009900;">&#40;</span> <span style="color: #0000ff;">@attrs</span> <span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span></span><span style="display:block;background-color: #ffc;"><span style="color: #0000ff;">$t</span><span style="color: #339933;">-&gt;</span><span style="color: #006600;">addRow</span><span style="color: #009900;">&#40;</span> <span style="color: #339933;">@</span><span style="color: #0000ff;">$_</span> <span style="color: #009900;">&#41;</span> <span style="color: #b1b100;">for</span> <span style="color: #009900;">&#40;</span><span style="color: #0000ff;">@langs</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span></span>&nbsp;
    <span style="color: #000066;">print</span> <span style="color: #0000ff;">$t</span><span style="color: #339933;">;</span></pre></td></tr></table><p class="theCode" style="display:none;">use strict;
    use warnings;
    use Text::ASCIITable;
    
    my @attrs = qw/NAME AUTHOR BIRTH VERSION WEBSITE/;
    
    my @langs = 
    (
        ['Perl','Larry Wall','1987','5.18.2','http://www.perl.org'],
        ['Python','Guido Van Rossum','1991','2.7.6','http://www.python.org'],
    );
    
    my $t = Text::ASCIITable-&gt;new({ headingText =&gt; 'Program Languages', drawRowLine =&gt; 1 });
    $t-&gt;setCols( @attrs );
    $t-&gt;addRow( @$_ ) for (@langs);
    
    print $t;</p></div>
    ";}
categories:
  - 代码卷轴
tags:
  - perl
  - 表格

---
前些日子利用公司内部项目提供的 RESTful API 封装了一个 CLI 脚本。其中用到不少有趣的 CPAN 模块，Text::ASCIITable 就是其中一个。

<a href="http://search.cpan.org/~lunatic/Text-ASCIITable-0.20/lib/Text/ASCIITable.pm" title="Perl模块Text::ASCIITable" target="_blank">Text::ASCIITable</a> 是一个用来将数据以纯文本格式的表格形式输出的 Perl 模块，表格样式简洁明了，而且可以灵活地自定义，非常适合命令行程序。我的这个 CLI 脚本需要将 Hash Ref 输出到终端，简单地使用 print 输出最多只能达到能看的效果，但是使用 Text::ASCIITable 能够做到一目了然。这个模块的接口也非常简单，稍微看看 POD 和 Example 就能上手。

<!--more-->

<pre lang='perl' line='1' highlight='13,14,15'>use strict;
use warnings;
use Text::ASCIITable;

my @attrs = qw/NAME AUTHOR BIRTH VERSION WEBSITE/;

my @langs = 
(
    ['Perl','Larry Wall','1987','5.18.2','http://www.perl.org'],
    ['Python','Guido Van Rossum','1991','2.7.6','http://www.python.org'],
);

my $t = Text::ASCIITable->new({ headingText => 'Program Languages', drawRowLine => 1 });
$t->setCols( @attrs );
$t->addRow( @$_ ) for (@langs);

print $t;
</pre>

以上Perl代码的输出结果如下图：

<img src="https://www.digglife.net/wp-content/uploads/2014/02/perl-asciitable-output-500x280.png" alt="Text::ASCIITable输出纯文本表格" width="500" height="280" class="alignnone size-medium wp-image-3776" />

Text::ASCIITable还有很多选项，比如上面这段有用到的 drawRowLine 会在每行数据后打印一条分割线。经常会使用的还会有：

  1. alignCol
上面的结果中，数字自动向右对齐了，可是我希望版本号被当作字符串处理，向左对其，可以加一句 `$t->alighCol('VERSION','left')`。除此之外，表头也能用 `alignHeadRow` 或者 `alignColName` 来处理。

  2. setColWidth
有时候一行字符太多，超过了终端宽度，可以用 `setColWidth` 来限制列宽，还可以使用 `drawPage` 来分页显示。

具体使用方式和选项，代码的POD里有详细描述，基本上能够满足一般使用需求。如果要UTF-8，颜色等更加丰富的功能，可以使用另外一个模块 <a href="http://search.cpan.org/~sharyanto/Text-ANSITable-0.26/lib/Text/ANSITable.pm" title="Perl模块Text::ASCIITable" target="_blank">Text::ANSITable</a>。
