---
title: 如何让WordPress模板在不同页面显示不同侧边栏
author: 摩摩诘
type: post
date: 2007-08-24T03:48:30+00:00
url: /articles/different-sidebar-in-different-pages.html
ratings_users:
  - 0
  - 0
ratings_score:
  - 0
  - 0
ratings_average:
  - 0
  - 0
0:
  - 05717cbacadeaeedacea6811f080c1f00c179b06a6126d4f1af59aa191f6b92dd06e801c8f39bee79957dd75a0bcdb28
  - 05717cbacadeaeedacea6811f080c1f00c179b06a6126d4f1af59aa191f6b92dd06e801c8f39bee79957dd75a0bcdb28
1:
  - cad918c882374109b36a0b7bab96ae1bca19f300c5d4706d7b1622274a91f37614f087c83ae85ac9e3d8156f73a44e35
  - cad918c882374109b36a0b7bab96ae1bca19f300c5d4706d7b1622274a91f37614f087c83ae85ac9e3d8156f73a44e35
2:
  - 84cadd616bc9b73d2bf459ad4a94d7f56e2c629979bc4c2002c3c27e8a06cbd5f7b555dba30afb2a6cb93ed0519fd579
  - 84cadd616bc9b73d2bf459ad4a94d7f56e2c629979bc4c2002c3c27e8a06cbd5f7b555dba30afb2a6cb93ed0519fd579
3:
  - 7ade81eb6f728db9befc7bed1338a33980c3fce9a4a97e506720ddc3105967728317843edb74074191c867c8c0b8d423
  - 7ade81eb6f728db9befc7bed1338a33980c3fce9a4a97e506720ddc3105967728317843edb74074191c867c8c0b8d423
4:
  - 9cac78c2e217f55cc740e7bc4c549149422767efcbb544dd021f827a65d2a5bef0c12b4c92c624bdfe2de57b8e5b3f86
  - 9cac78c2e217f55cc740e7bc4c549149422767efcbb544dd021f827a65d2a5bef0c12b4c92c624bdfe2de57b8e5b3f86
5:
  - 503dd49cabf0d03f0ef8fef05fd494a11b57ca8dc5cbd8f703ff4a1abb7ebd88adc1ed117b5053b4694a3bed831c9e6a
  - 503dd49cabf0d03f0ef8fef05fd494a11b57ca8dc5cbd8f703ff4a1abb7ebd88adc1ed117b5053b4694a3bed831c9e6a
comment_count:
  - 6
trackback_count:
  - 1
related_posts:
  - 'a:2:{s:4:"time";i:1224852234;s:13:"related_posts";s:1375:"<h3>相关日志</h3><ul class="related_post"><li><a href="http://www.digglife.cn/articles/sidebar-widgets-support.html" title="如何让Wordpress模板支持Sidebar Widgets(侧边栏插件)">如何让Wordpress模板支持Sidebar Widgets(侧边栏插件)</a></li><li><a href="http://www.digglife.cn/articles/about-wordpress26-image-caption.html" title="关于Wordpress2.6的图片说明(image Captioin)">关于Wordpress2.6的图片说明(image Captioin)</a></li><li><a href="http://www.digglife.cn/articles/can-not-modify-category-slug.html" title="Wordpress无法编辑分类缩略名(Slug)的解决">Wordpress无法编辑分类缩略名(Slug)的解决</a></li><li><a href="http://www.digglife.cn/articles/backup-windows-live-writer.html" title="如何全面备份Windows Live Writer">如何全面备份Windows Live Writer</a></li><li><a href="http://www.digglife.cn/articles/manage-multiple-accouts-without-logging-off.html" title="同时管理同一网站的不同帐户:CookieSwap">同时管理同一网站的不同帐户:CookieSwap</a></li><li><a href="http://www.digglife.cn/articles/digglife-new-theme-online.html" title="DiggLife新主题Beta中&#8230;">DiggLife新主题Beta中&#8230;</a></li><li><a href="http://www.digglife.cn/articles/wordpress-comment-notifier.html" title="桌面版Wordpress评论提醒工具">桌面版Wordpress评论提醒工具</a></li></ul>";}'
views:
  - 4618
bot_views:
  - 2414
duoshuo_thread_id:
  - 1154125469839261901
wp-syntax-cache-content:
  - |
    a:4:{i:1;s:7233:"
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
    18
    19
    20
    21
    22
    23
    24
    25
    26
    27
    28
    29
    30
    31
    32
    33
    34
    35
    36
    37
    38
    39
    40
    </pre></td><td class="code"><pre class="css" style="font-family:monospace;">&nbsp;
    &lt; ?php
    // 默认的侧边栏定义
    if <span style="color: #00AA00;">&#40;</span> function_exists<span style="color: #00AA00;">&#40;</span><span style="color: #ff0000;">'register_sidebar'</span><span style="color: #00AA00;">&#41;</span> <span style="color: #00AA00;">&#41;</span>
    register_sidebar<span style="color: #00AA00;">&#40;</span>array<span style="color: #00AA00;">&#40;</span>
    <span style="color: #ff0000;">'name'</span> <span style="color: #00AA00;">=&gt;</span> <span style="color: #ff0000;">'Left Sidebar'</span><span style="color: #00AA00;">,</span>
    <span style="color: #ff0000;">'before_widget'</span> <span style="color: #00AA00;">=&gt;</span> <span style="color: #ff0000;">'&lt;li&gt;'</span><span style="color: #00AA00;">,</span>
    <span style="color: #ff0000;">'after_widget'</span> <span style="color: #00AA00;">=&gt;</span> <span style="color: #ff0000;">'&lt;/li&gt;'</span><span style="color: #00AA00;">,</span>
    <span style="color: #ff0000;">'before_title'</span> <span style="color: #00AA00;">=&gt;</span> <span style="color: #ff0000;">'&lt;h3&gt;'</span><span style="color: #00AA00;">,</span>
    <span style="color: #ff0000;">'after_title'</span> <span style="color: #00AA00;">=&gt;</span> <span style="color: #ff0000;">'&lt;/h3&gt;'</span><span style="color: #00AA00;">,</span>
    <span style="color: #00AA00;">&#41;</span><span style="color: #00AA00;">&#41;</span><span style="color: #00AA00;">;</span>
    &nbsp;
    if <span style="color: #00AA00;">&#40;</span> function_exists<span style="color: #00AA00;">&#40;</span><span style="color: #ff0000;">'register_sidebar'</span><span style="color: #00AA00;">&#41;</span> <span style="color: #00AA00;">&#41;</span>
    register_sidebar<span style="color: #00AA00;">&#40;</span>array<span style="color: #00AA00;">&#40;</span>
    <span style="color: #ff0000;">'name'</span> <span style="color: #00AA00;">=&gt;</span> <span style="color: #ff0000;">'Right Sidebar'</span><span style="color: #00AA00;">,</span>
    <span style="color: #ff0000;">'before_widget'</span> <span style="color: #00AA00;">=&gt;</span> <span style="color: #ff0000;">'&lt;li&gt;'</span><span style="color: #00AA00;">,</span>
    <span style="color: #ff0000;">'after_widget'</span> <span style="color: #00AA00;">=&gt;</span> <span style="color: #ff0000;">'&lt;/li&gt;'</span><span style="color: #00AA00;">,</span>
    <span style="color: #ff0000;">'before_title'</span> <span style="color: #00AA00;">=&gt;</span> <span style="color: #ff0000;">'&lt;h3&gt;'</span><span style="color: #00AA00;">,</span>
    <span style="color: #ff0000;">'after_title'</span> <span style="color: #00AA00;">=&gt;</span> <span style="color: #ff0000;">'&lt;/h3&gt;'</span><span style="color: #00AA00;">,</span>
    <span style="color: #00AA00;">&#41;</span><span style="color: #00AA00;">&#41;</span><span style="color: #00AA00;">;</span>
    &nbsp;
    //以下为文章页侧边栏定义.
    &nbsp;
    if <span style="color: #00AA00;">&#40;</span> function_exists<span style="color: #00AA00;">&#40;</span><span style="color: #ff0000;">'register_sidebar'</span><span style="color: #00AA00;">&#41;</span> <span style="color: #00AA00;">&#41;</span>
    register_sidebar<span style="color: #00AA00;">&#40;</span>array<span style="color: #00AA00;">&#40;</span>
    <span style="color: #ff0000;">'name'</span> <span style="color: #00AA00;">=&gt;</span> <span style="color: #ff0000;">'Left Sidebar2'</span><span style="color: #00AA00;">,</span>   //name值自行定义
    <span style="color: #ff0000;">'before_widget'</span> <span style="color: #00AA00;">=&gt;</span> <span style="color: #ff0000;">'&lt;li&gt;'</span><span style="color: #00AA00;">,</span>
    <span style="color: #ff0000;">'after_widget'</span> <span style="color: #00AA00;">=&gt;</span> <span style="color: #ff0000;">'&lt;/li&gt;'</span><span style="color: #00AA00;">,</span>
    <span style="color: #ff0000;">'before_title'</span> <span style="color: #00AA00;">=&gt;</span> <span style="color: #ff0000;">'&lt;h3&gt;'</span><span style="color: #00AA00;">,</span>
    <span style="color: #ff0000;">'after_title'</span> <span style="color: #00AA00;">=&gt;</span> <span style="color: #ff0000;">'&lt;/h3&gt;'</span><span style="color: #00AA00;">,</span>
    <span style="color: #00AA00;">&#41;</span><span style="color: #00AA00;">&#41;</span><span style="color: #00AA00;">;</span>
    &nbsp;
    if <span style="color: #00AA00;">&#40;</span> function_exists<span style="color: #00AA00;">&#40;</span><span style="color: #ff0000;">'register_sidebar'</span><span style="color: #00AA00;">&#41;</span> <span style="color: #00AA00;">&#41;</span>
    register_sidebar<span style="color: #00AA00;">&#40;</span>array<span style="color: #00AA00;">&#40;</span>
    <span style="color: #ff0000;">'name'</span> <span style="color: #00AA00;">=&gt;</span> <span style="color: #ff0000;">'Right Sidebar2'</span><span style="color: #00AA00;">,</span> //name值自行定义
    <span style="color: #ff0000;">'before_widget'</span> <span style="color: #00AA00;">=&gt;</span> <span style="color: #ff0000;">'&lt;li&gt;'</span><span style="color: #00AA00;">,</span>
    <span style="color: #ff0000;">'after_widget'</span> <span style="color: #00AA00;">=&gt;</span> <span style="color: #ff0000;">'&lt;/li&gt;'</span><span style="color: #00AA00;">,</span>
    <span style="color: #ff0000;">'before_title'</span> <span style="color: #00AA00;">=&gt;</span> <span style="color: #ff0000;">'&lt;h3&gt;'</span><span style="color: #00AA00;">,</span>
    <span style="color: #ff0000;">'after_title'</span> <span style="color: #00AA00;">=&gt;</span> <span style="color: #ff0000;">'&lt;/h3&gt;'</span><span style="color: #00AA00;">,</span>
    <span style="color: #00AA00;">&#41;</span><span style="color: #00AA00;">&#41;</span><span style="color: #00AA00;">;</span>?<span style="color: #00AA00;">&gt;</span></pre></td></tr></table><p class="theCode" style="display:none;">
    &lt; ?php
    // 默认的侧边栏定义
    if ( function_exists('register_sidebar') )
    register_sidebar(array(
    'name' =&gt; 'Left Sidebar',
    'before_widget' =&gt; '&lt;li&gt;',
    'after_widget' =&gt; '&lt;/li&gt;',
    'before_title' =&gt; '&lt;h3&gt;',
    'after_title' =&gt; '&lt;/h3&gt;',
    ));
    
    if ( function_exists('register_sidebar') )
    register_sidebar(array(
    'name' =&gt; 'Right Sidebar',
    'before_widget' =&gt; '&lt;li&gt;',
    'after_widget' =&gt; '&lt;/li&gt;',
    'before_title' =&gt; '&lt;h3&gt;',
    'after_title' =&gt; '&lt;/h3&gt;',
    ));
    
    //以下为文章页侧边栏定义.
    
    if ( function_exists('register_sidebar') )
    register_sidebar(array(
    'name' =&gt; 'Left Sidebar2',   //name值自行定义
    'before_widget' =&gt; '&lt;li&gt;',
    'after_widget' =&gt; '&lt;/li&gt;',
    'before_title' =&gt; '&lt;h3&gt;',
    'after_title' =&gt; '&lt;/h3&gt;',
    ));
    
    if ( function_exists('register_sidebar') )
    register_sidebar(array(
    'name' =&gt; 'Right Sidebar2', //name值自行定义
    'before_widget' =&gt; '&lt;li&gt;',
    'after_widget' =&gt; '&lt;/li&gt;',
    'before_title' =&gt; '&lt;h3&gt;',
    'after_title' =&gt; '&lt;/h3&gt;',
    ));?&gt;</p></div>
    ";i:2;s:1295:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="line_numbers"><pre>1
    2
    </pre></td><td class="code"><pre class="php" style="font-family:monospace;"><span style="color: #339933;">&lt;</span> ?php <span style="color: #b1b100;">if</span> <span style="color: #009900;">&#40;</span> <span style="color: #990000;">function_exists</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'dynamic_sidebar'</span><span style="color: #009900;">&#41;</span> <span style="color: #339933;">&amp;&amp;</span> dynamic_sidebar<span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'#7'</span><span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#41;</span> <span style="color: #339933;">:</span> <span style="color: #b1b100;">else</span> <span style="color: #339933;">:</span> <span style="color: #000000; font-weight: bold;">?&gt;</span>
    <span style="color: #339933;">&lt;</span> ?php <span style="color: #b1b100;">endif</span><span style="color: #339933;">;</span> <span style="color: #000000; font-weight: bold;">?&gt;</span></pre></td></tr></table><p class="theCode" style="display:none;">&lt; ?php if ( function_exists('dynamic_sidebar') &amp;&amp; dynamic_sidebar('#7') ) : else : ?&gt;
    &lt; ?php endif; ?&gt;</p></div>
    ";i:3;s:4040:"
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
    </pre></td><td class="code"><pre class="php" style="font-family:monospace;"><span style="color: #339933;">&lt;</span>div id<span style="color: #339933;">=</span><span style="color: #0000ff;">&quot;sidebar&quot;</span><span style="color: #339933;">&gt;</span>
    <span style="color: #339933;">&lt;</span>div id<span style="color: #339933;">=</span><span style="color: #0000ff;">&quot;sidebar_r&quot;</span><span style="color: #339933;">&gt;</span><span style="color: #666666; font-style: italic;">//右侧栏</span>
    <span style="color: #339933;">&lt;</span>ul<span style="color: #339933;">&gt;</span> <span style="color: #339933;">&lt;</span> ?php <span style="color: #b1b100;">if</span> <span style="color: #009900;">&#40;</span> <span style="color: #990000;">function_exists</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'dynamic_sidebar'</span><span style="color: #009900;">&#41;</span> <span style="color: #339933;">&amp;&amp;</span> dynamic_sidebar<span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'Right Sidebar2'</span><span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#41;</span> <span style="color: #339933;">:</span> <span style="color: #b1b100;">else</span> <span style="color: #339933;">:</span> <span style="color: #000000; font-weight: bold;">?&gt;</span>
    <span style="color: #339933;">......</span>
    <span style="color: #339933;">&lt;</span> ?php <span style="color: #b1b100;">endif</span><span style="color: #339933;">;</span> <span style="color: #000000; font-weight: bold;">?&gt;</span><span style="color: #339933;">&lt;/</span>ul<span style="color: #339933;">&gt;</span>
    <span style="color: #339933;">&lt;/</span>div<span style="color: #339933;">&gt;</span>
    &nbsp;
    <span style="color: #339933;">&lt;</span>div id<span style="color: #339933;">=</span><span style="color: #0000ff;">&quot;sidebar_l&quot;</span><span style="color: #339933;">&gt;</span><span style="color: #666666; font-style: italic;">//左侧栏</span>
    <span style="color: #339933;">&lt;</span>ul<span style="color: #339933;">&gt;</span> <span style="color: #339933;">&lt;</span> ?php <span style="color: #b1b100;">if</span> <span style="color: #009900;">&#40;</span> <span style="color: #990000;">function_exists</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'dynamic_sidebar'</span><span style="color: #009900;">&#41;</span> <span style="color: #339933;">&amp;&amp;</span> dynamic_sidebar<span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'Left Sidebar2'</span><span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#41;</span> <span style="color: #339933;">:</span> <span style="color: #b1b100;">else</span> <span style="color: #339933;">:</span> <span style="color: #000000; font-weight: bold;">?&gt;</span>
    <span style="color: #339933;">......</span>
    <span style="color: #339933;">&lt;</span> ?php <span style="color: #b1b100;">endif</span><span style="color: #339933;">;</span> <span style="color: #000000; font-weight: bold;">?&gt;</span><span style="color: #339933;">&lt;/</span>ul<span style="color: #339933;">&gt;</span>
    <span style="color: #339933;">&lt;/</span>div<span style="color: #339933;">&gt;</span>
    <span style="color: #339933;">&lt;/</span>div<span style="color: #339933;">&gt;</span></pre></td></tr></table><p class="theCode" style="display:none;">&lt;div id=&quot;sidebar&quot;&gt;
    &lt;div id=&quot;sidebar_r&quot;&gt;//右侧栏
    &lt;ul&gt; &lt; ?php if ( function_exists('dynamic_sidebar') &amp;&amp; dynamic_sidebar('Right Sidebar2') ) : else : ?&gt;
    ......
    &lt; ?php endif; ?&gt;&lt;/ul&gt;
    &lt;/div&gt;
    
    &lt;div id=&quot;sidebar_l&quot;&gt;//左侧栏
    &lt;ul&gt; &lt; ?php if ( function_exists('dynamic_sidebar') &amp;&amp; dynamic_sidebar('Left Sidebar2') ) : else : ?&gt;
    ......
    &lt; ?php endif; ?&gt;&lt;/ul&gt;
    &lt;/div&gt;
    &lt;/div&gt;</p></div>
    ";i:4;s:683:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="line_numbers"><pre>1
    </pre></td><td class="code"><pre class="php" style="font-family:monospace;"><span style="color: #339933;">&lt;</span> ?php <span style="color: #b1b100;">include_once</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">&quot;sidebar2.php &quot;</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span> <span style="color: #000000; font-weight: bold;">?&gt;</span><span style="color: #339933;">.</span></pre></td></tr></table><p class="theCode" style="display:none;">&lt; ?php include_once(&quot;sidebar2.php &quot;); ?&gt;.</p></div>
    ";}
categories:
  - 博客研究
tags:
  - sidebar
  - widgets
  - wordpress
  - 侧边栏
  - 插件

---
<img src="http://digglife.qiniudn.com/qiniu/1654/image/45c87639107817a6379391a581a6934f.jpg" border="0" alt="wordpress_logo" width="70" height="70" align="right" />很多人喜欢在不同的页面显示不同的侧边,事实上这的确非常管用,比如你为了访客体验不想把广告显示在首页而更愿意放在文章页,这就非常需要把index.php和single.php的侧边区别起来.有了<a title="如何让wordpress模板支持侧边栏插件(sidebar widget)" href="https://www.digglife.net/articles/sidebar-widgets-support.html" target="_blank">上一篇</a>做基础,这个实现起来其实非常简单.很多博主采取的是在functions.php中的**&#8220;register_sidebar(&#8220;**后添加数字,这种方法也非常好,但是对于三栏模板需要将侧栏的两列分别建立不同的sidebar文件,那么要实现不同的侧栏你需要建立4个sidebar.相比这个方法,我更加喜欢直接在functions.php中直接添加sidebar定义.下面拿我修改的那个**三栏模板**作为示例:

(\****以下代码在Feed阅读器中可能会有问题,如果感兴趣建议到原网页.)

<!--more-->

**1.修改functions.php.**

三栏模板本身应该只有两个sidebar定义,现在我们再给它添加两个.

<pre lang="css" line="1">&lt; ?php
// 默认的侧边栏定义
if ( function_exists('register_sidebar') )
register_sidebar(array(
'name' => 'Left Sidebar',
'before_widget' => '

<li>
  ',
  'after_widget' => '
</li>',
'before_title' => '

<h3>
  ',
  'after_title' => '
</h3>',
));

if ( function_exists('register_sidebar') )
register_sidebar(array(
'name' => 'Right Sidebar',
'before_widget' => '

<li>
  ',
  'after_widget' => '
</li>',
'before_title' => '

<h3>
  ',
  'after_title' => '
</h3>',
));

//以下为文章页侧边栏定义.

if ( function_exists('register_sidebar') )
register_sidebar(array(
'name' => 'Left Sidebar2',   //name值自行定义
'before_widget' => '

<li>
  ',
  'after_widget' => '
</li>',
'before_title' => '

<h3>
  ',
  'after_title' => '
</h3>',
));

if ( function_exists('register_sidebar') )
register_sidebar(array(
'name' => 'Right Sidebar2', //name值自行定义
'before_widget' => '

<li>
  ',
  'after_widget' => '
</li>',
'before_title' => '

<h3>
  ',
  'after_title' => '
</h3>',
));?>
</pre>

**2.新建一个sidebar2.php**(文件名可以自己取,我只是举个例子),复制默认的sidebar.php中的所有文件并粘贴进来(当然是已经支持Widgets的那个),并修改下面的代码中的**#7**为Functons.php文件中新加入的Sidebar的name.

<pre lang="php" line="1">&lt; ?php if ( function_exists('dynamic_sidebar') &#038;&#038; dynamic_sidebar('#7') ) : else : ?>
&lt; ?php endif; ?>
</pre>

所以我的模板中的两段代码应该为:

<pre lang="php" line="1"><div id="sidebar">
  <div id="sidebar_r">
    //右侧栏
    
    
    <ul>
      &lt; ?php if ( function_exists('dynamic_sidebar') &#038;&#038; dynamic_sidebar('Right Sidebar2') ) : else : ?>
      ......
      &lt; ?php endif; ?>
    </ul>
    
  </div>
  
  
  
  <div id="sidebar_l">
    //左侧栏
    
    
    <ul>
      &lt; ?php if ( function_exists('dynamic_sidebar') &#038;&#038; dynamic_sidebar('Left Sidebar2') ) : else : ?>
      ......
      &lt; ?php endif; ?>
    </ul>
    
  </div>
  
</div>
</pre>

**3.修改single.php文件.**

在single.php中找到<span style="background-color: #ff9900;">< ?php get_sidebar(); ? ></span>,删除之,改为:

<pre lang="php" line="1">&lt; ?php include_once("sidebar2.php "); ?>.
</pre>

保存退出.如果你还想修改Page.php等页面的话,可以使用同样的方法.

登入后台的侧边栏区块,你就会发现已经出现了4个Widgets,给它们分别添加不同的内容,就可以实现在不同的页面显示不同的侧边栏了.

**4.总结:**

在网上流传比较广泛的是将functions.php中的<span style="background-color: #ff9900;">&#8220;register_sidebar(array(&#8220;</span>改为<span style="background-color: #ff9900;">&#8220;register_sidebar(4, array(&#8220;</span>的模式,并创建4个sidebar文件,具体方法好多人都有介绍,推荐一个:

<a href="http://zeuscn.net/" target="_blank">zEUS</a>的<a href="http://zeuscn.net/archives/2007/08/11/update-sidebar-widget/" target="_blank">WP自带Sidebar Widgets的终极改造</a>

这种方法其实更加专业,但是我觉得不如我上面说的直观和傻瓜化.

我本来想把DiggLife的模板也改为这种模式,但是还没有想好该放什么东西,本来目前的侧边该怎样放我一直都在犹豫呢.