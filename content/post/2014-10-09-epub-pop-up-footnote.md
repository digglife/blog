---
title: EPUB弹出窗口式脚注
author: 摩摩诘
type: post
date: 2014-10-08T16:45:35+00:00
excerpt: 网上搜到一些国学典籍的 EPUB 版，虽有古人的注解，但正文和注解混排在一起，影响正常阅读，于是研究了一下 EPUB3 中有关脚注（footnote）的规格定义，写了一个 Python 脚本把所有混在正文中的脚注全部改写成了弹出窗口样式，在 iBooks 里测试通过，略记一笔。
url: /articles/epub-pop-up-footnote.html
index_image:
  - https://www.digglife.net/wp-content/uploads/2014/10/epub-footnote.png
views:
  - 1350
duoshuo_thread_id:
  - 1154125469839262195
wp-syntax-cache-content:
  - |
    a:6:{i:1;s:792:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="html" style="font-family:monospace;">&lt;p&gt;
    太祖武皇帝，沛國譙人也，姓曹，諱操，字孟德，漢相國參之後。
        &lt;a epub:type=&quot;noteref&quot; href=&quot;#fn1&quot;&gt;
            &lt;sup&gt;1&lt;/sup&gt;
        &lt;/a&gt;
    桓帝世，曹騰為中常侍大長秋，封費亭侯。
    ......
    &lt;/p&gt;</pre></td></tr></table><p class="theCode" style="display:none;">&lt;p&gt;
    太祖武皇帝，沛國譙人也，姓曹，諱操，字孟德，漢相國參之後。
        &lt;a epub:type=&quot;noteref&quot; href=&quot;#fn1&quot;&gt;
            &lt;sup&gt;1&lt;/sup&gt;
        &lt;/a&gt;
    桓帝世，曹騰為中常侍大長秋，封費亭侯。
    ......
    &lt;/p&gt;</p></div>
    ";i:2;s:1152:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="html" style="font-family:monospace;">&lt;aside epub:type=&quot;footnote&quot; id=&quot;fn1&quot;&gt;
    〔曹瞞傳曰：太祖一名吉利，小字阿瞞。王沈魏書曰：其先出於黃帝。當高陽世，陸終之子曰安，是為曹姓。周武王克殷，存先世之後，封曹俠於邾。春秋之世，與於盟會，逮至戰國，為楚所滅。子孫分流，或家於沛。漢高祖之起，曹參以功封平陽侯，世襲爵士，絶而復紹，至今適嗣國於容城。〕
    &lt;/aside&gt;</pre></td></tr></table><p class="theCode" style="display:none;">&lt;aside epub:type=&quot;footnote&quot; id=&quot;fn1&quot;&gt;
    〔曹瞞傳曰：太祖一名吉利，小字阿瞞。王沈魏書曰：其先出於黃帝。當高陽世，陸終之子曰安，是為曹姓。周武王克殷，存先世之後，封曹俠於邾。春秋之世，與於盟會，逮至戰國，為楚所滅。子孫分流，或家於沛。漢高祖之起，曹參以功封平陽侯，世襲爵士，絶而復紹，至今適嗣國於容城。〕
    &lt;/aside&gt;</p></div>
    ";i:3;s:598:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="html" style="font-family:monospace;">&lt;html xml:lang=&quot;zh-CN&quot; xmlns=&quot;http://www.w3.org/1999/xhtml&quot; xmlns:xml=&quot;http://www.w3.org/XML/1998/namespace&quot; xmlns:epub=&quot;http://www.idpf.org/2007/ops&quot;&gt;</pre></td></tr></table><p class="theCode" style="display:none;">&lt;html xml:lang=&quot;zh-CN&quot; xmlns=&quot;http://www.w3.org/1999/xhtml&quot; xmlns:xml=&quot;http://www.w3.org/XML/1998/namespace&quot; xmlns:epub=&quot;http://www.idpf.org/2007/ops&quot;&gt;</p></div>
    ";i:4;s:1468:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="html" style="font-family:monospace;">&lt;p&gt;太祖武皇帝，沛國譙人也，姓曹，諱操，字孟德，漢相國參之後。
        &lt;span class=&quot;zhushi&quot;&gt;
    〔曹瞞傳曰：太祖一名吉利，小字阿瞞。王沈魏書曰：其先出於黃帝。當高陽世，陸終之子曰安，是為曹姓。周武王克殷，存先世之後，封曹俠於邾。春秋之世，與於盟會，逮至戰國，為楚所滅。子孫分流，或家於沛。漢高祖之起，曹參以功封平陽侯，世襲爵士，絶而復紹，至今適嗣國於容城。〕
        &lt;/span&gt;
    桓帝世，曹騰為中常侍大長秋，封費亭侯。
    ......
    &lt;/p&gt;</pre></td></tr></table><p class="theCode" style="display:none;">&lt;p&gt;太祖武皇帝，沛國譙人也，姓曹，諱操，字孟德，漢相國參之後。
        &lt;span class=&quot;zhushi&quot;&gt;
    〔曹瞞傳曰：太祖一名吉利，小字阿瞞。王沈魏書曰：其先出於黃帝。當高陽世，陸終之子曰安，是為曹姓。周武王克殷，存先世之後，封曹俠於邾。春秋之世，與於盟會，逮至戰國，為楚所滅。子孫分流，或家於沛。漢高祖之起，曹參以功封平陽侯，世襲爵士，絶而復紹，至今適嗣國於容城。〕
        &lt;/span&gt;
    桓帝世，曹騰為中常侍大長秋，封費亭侯。
    ......
    &lt;/p&gt;</p></div>
    ";i:5;s:9574:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="python" style="font-family:monospace;"><span style="color: #808080; font-style: italic;">#!/usr/bin/python</span>
    <span style="color: #808080; font-style: italic;"># -*- coding: utf-8 -*-</span>
    &nbsp;
    <span style="color: #ff7700;font-weight:bold;">from</span> bs4 <span style="color: #ff7700;font-weight:bold;">import</span> BeautifulSoup
    <span style="color: #ff7700;font-weight:bold;">import</span> <span style="color: #dc143c;">os</span>
    &nbsp;
    epub_content_path <span style="color: #66cc66;">=</span> <span style="color: #483d8b;">'/Users/erichu/dev/guoxue/sanguo.epub/OEBPS/Text'</span>
    &nbsp;
    <span style="color: #ff7700;font-weight:bold;">for</span> f <span style="color: #ff7700;font-weight:bold;">in</span> <span style="color: #dc143c;">os</span>.<span style="color: black;">listdir</span><span style="color: black;">&#40;</span>epub_content_path<span style="color: black;">&#41;</span>:
        html <span style="color: #66cc66;">=</span> <span style="color: #dc143c;">os</span>.<span style="color: black;">path</span>.<span style="color: black;">join</span><span style="color: black;">&#40;</span>epub_content_path<span style="color: #66cc66;">,</span>f<span style="color: black;">&#41;</span>
        <span style="color: #ff7700;font-weight:bold;">print</span> html
        doc <span style="color: #66cc66;">=</span> <span style="color: #008000;">open</span><span style="color: black;">&#40;</span>html<span style="color: #66cc66;">,</span><span style="color: #483d8b;">'rb'</span><span style="color: black;">&#41;</span>
        soup <span style="color: #66cc66;">=</span> BeautifulSoup<span style="color: black;">&#40;</span>doc<span style="color: black;">&#41;</span>
    &nbsp;
        <span style="color: #808080; font-style: italic;">#如果没有HTML标签里没有定义epub namespace，则加上</span>
        <span style="color: #ff7700;font-weight:bold;">if</span> <span style="color: #ff7700;font-weight:bold;">not</span> <span style="color: #483d8b;">'xmlns:epub'</span> <span style="color: #ff7700;font-weight:bold;">in</span> soup.<span style="color: black;">html</span>.<span style="color: black;">attrs</span>:
            soup.<span style="color: black;">html</span><span style="color: black;">&#91;</span><span style="color: #483d8b;">'xmlns:epub'</span><span style="color: black;">&#93;</span> <span style="color: #66cc66;">=</span> <span style="color: #483d8b;">&quot;http://www.idpf.org/2007/ops&quot;</span>
    &nbsp;
        <span style="color: #808080; font-style: italic;">#没有使用soup.find_all('span')是为了略过&lt;span&gt;中内嵌&lt;span&gt;的情况</span>
        notes <span style="color: #66cc66;">=</span> soup.<span style="color: #dc143c;">select</span><span style="color: black;">&#40;</span><span style="color: #483d8b;">'p &gt; span'</span><span style="color: black;">&#41;</span>
    &nbsp;
        <span style="color: #808080; font-style: italic;">#如果没有找到span标签，进入下一个循环</span>
        <span style="color: #ff7700;font-weight:bold;">if</span> <span style="color: #ff7700;font-weight:bold;">not</span> notes:
            <span style="color: #ff7700;font-weight:bold;">continue</span>
        <span style="color: #808080; font-style: italic;">#反序循环 notes 列表</span>
        <span style="color: #ff7700;font-weight:bold;">for</span> n <span style="color: #ff7700;font-weight:bold;">in</span> <span style="color: #008000;">range</span><span style="color: black;">&#40;</span><span style="color: #008000;">len</span><span style="color: black;">&#40;</span>notes<span style="color: black;">&#41;</span>-<span style="color: #ff4500;">1</span><span style="color: #66cc66;">,</span> -<span style="color: #ff4500;">1</span><span style="color: #66cc66;">,</span> -<span style="color: #ff4500;">1</span><span style="color: black;">&#41;</span>:
            <span style="color: #808080; font-style: italic;">#n是列表index，number是实际注释序号</span>
            note <span style="color: #66cc66;">=</span> notes<span style="color: black;">&#91;</span>n<span style="color: black;">&#93;</span>
            number <span style="color: #66cc66;">=</span> n+<span style="color: #ff4500;">1</span>
    &nbsp;
            footnote <span style="color: #66cc66;">=</span> soup.<span style="color: black;">new_tag</span><span style="color: black;">&#40;</span><span style="color: #483d8b;">'aside'</span><span style="color: black;">&#41;</span>
            footnote<span style="color: black;">&#91;</span><span style="color: #483d8b;">'epub:type'</span><span style="color: black;">&#93;</span> <span style="color: #66cc66;">=</span> <span style="color: #483d8b;">'footnote'</span>
            footnote<span style="color: black;">&#91;</span><span style="color: #483d8b;">'id'</span><span style="color: black;">&#93;</span> <span style="color: #66cc66;">=</span> <span style="color: #483d8b;">'fn%d'</span> % number
            footnote.<span style="color: #dc143c;">string</span> <span style="color: #66cc66;">=</span> note.<span style="color: black;">get_text</span><span style="color: black;">&#40;</span><span style="color: black;">&#41;</span>
            <span style="color: #808080; font-style: italic;">#为了保证aside模块是按数字顺序逐一插入到段落之后，所以反序读取notes列表</span>
            note.<span style="color: black;">parent</span>.<span style="color: black;">insert_after</span><span style="color: black;">&#40;</span>footnote<span style="color: black;">&#41;</span>
    &nbsp;
            note.<span style="color: black;">clear</span><span style="color: black;">&#40;</span><span style="color: black;">&#41;</span>
            note.<span style="color: black;">name</span> <span style="color: #66cc66;">=</span> <span style="color: #483d8b;">&quot;a&quot;</span>
            <span style="color: #ff7700;font-weight:bold;">del</span> note<span style="color: black;">&#91;</span><span style="color: #483d8b;">'class'</span><span style="color: black;">&#93;</span>
            note<span style="color: black;">&#91;</span><span style="color: #483d8b;">'epub:type'</span><span style="color: black;">&#93;</span> <span style="color: #66cc66;">=</span> <span style="color: #483d8b;">'noteref'</span>
            note<span style="color: black;">&#91;</span><span style="color: #483d8b;">'href'</span><span style="color: black;">&#93;</span> <span style="color: #66cc66;">=</span> <span style="color: #483d8b;">'#fn%d'</span> % number
            sup <span style="color: #66cc66;">=</span> soup.<span style="color: black;">new_tag</span><span style="color: black;">&#40;</span><span style="color: #483d8b;">'sup'</span><span style="color: black;">&#41;</span>
            sup.<span style="color: #dc143c;">string</span> <span style="color: #66cc66;">=</span> <span style="color: #008000;">str</span><span style="color: black;">&#40;</span>number<span style="color: black;">&#41;</span>
            note.<span style="color: black;">append</span><span style="color: black;">&#40;</span>sup<span style="color: black;">&#41;</span>
    &nbsp;
        <span style="color: #808080; font-style: italic;">#print soup.prettify()</span>
        doc.<span style="color: black;">close</span><span style="color: black;">&#40;</span><span style="color: black;">&#41;</span>
        doc <span style="color: #66cc66;">=</span> <span style="color: #008000;">open</span><span style="color: black;">&#40;</span>html<span style="color: #66cc66;">,</span><span style="color: #483d8b;">'wb'</span><span style="color: black;">&#41;</span>
        doc.<span style="color: black;">write</span><span style="color: black;">&#40;</span><span style="color: #008000;">str</span><span style="color: black;">&#40;</span>soup<span style="color: black;">&#41;</span><span style="color: black;">&#41;</span>
        doc.<span style="color: black;">close</span><span style="color: black;">&#40;</span><span style="color: black;">&#41;</span></pre></td></tr></table><p class="theCode" style="display:none;">#!/usr/bin/python
    # -*- coding: utf-8 -*-
    
    from bs4 import BeautifulSoup
    import os
    
    epub_content_path = '/Users/erichu/dev/guoxue/sanguo.epub/OEBPS/Text'
    
    for f in os.listdir(epub_content_path):
        html = os.path.join(epub_content_path,f)
        print html
        doc = open(html,'rb')
        soup = BeautifulSoup(doc)
    
        #如果没有HTML标签里没有定义epub namespace，则加上
        if not 'xmlns:epub' in soup.html.attrs:
            soup.html['xmlns:epub'] = &quot;http://www.idpf.org/2007/ops&quot;
    
        #没有使用soup.find_all('span')是为了略过&lt;span&gt;中内嵌&lt;span&gt;的情况
        notes = soup.select('p &gt; span')
    
        #如果没有找到span标签，进入下一个循环
        if not notes:
            continue
        #反序循环 notes 列表
        for n in range(len(notes)-1, -1, -1):
            #n是列表index，number是实际注释序号
            note = notes[n]
            number = n+1
    
            footnote = soup.new_tag('aside')
            footnote['epub:type'] = 'footnote'
            footnote['id'] = 'fn%d' % number
            footnote.string = note.get_text()
            #为了保证aside模块是按数字顺序逐一插入到段落之后，所以反序读取notes列表
            note.parent.insert_after(footnote)
    
            note.clear()
            note.name = &quot;a&quot;
            del note['class']
            note['epub:type'] = 'noteref'
            note['href'] = '#fn%d' % number
            sup = soup.new_tag('sup')
            sup.string = str(number)
            note.append(sup)
    
        #print soup.prettify()
        doc.close()
        doc = open(html,'wb')
        doc.write(str(soup))
        doc.close()</p></div>
    ";i:6;s:2797:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="css" style="font-family:monospace;">sup <span style="color: #00AA00;">&#123;</span>
        <span style="color: #000000; font-weight: bold;">font-family</span><span style="color: #00AA00;">:</span> Arial<span style="color: #00AA00;">;</span>
        <span style="color: #000000; font-weight: bold;">font-size</span><span style="color: #00AA00;">:</span> <span style="color: #933;">0.5em</span><span style="color: #00AA00;">;</span>
        <span style="color: #000000; font-weight: bold;">color</span><span style="color: #00AA00;">:</span><span style="color: #cc00cc;">#FFF</span><span style="color: #00AA00;">;</span>
        <span style="color: #000000; font-weight: bold;">background-color</span><span style="color: #00AA00;">:</span> <span style="color: #cc00cc;">#333</span><span style="color: #00AA00;">;</span>
        <span style="color: #000000; font-weight: bold;">display</span><span style="color: #00AA00;">:</span> <span style="color: #993333;">inline-block</span><span style="color: #00AA00;">;</span>
        <span style="color: #000000; font-weight: bold;">border-radius</span><span style="color: #00AA00;">:</span><span style="color: #933;">0.25em</span><span style="color: #00AA00;">;</span>
        <span style="color: #808080; font-style: italic;">/* reset text-indent */</span>
        <span style="color: #000000; font-weight: bold;">text-indent</span><span style="color: #00AA00;">:</span> <span style="color: #cc66cc;">0</span><span style="color: #00AA00;">;</span>
        <span style="color: #000000; font-weight: bold;">padding</span><span style="color: #00AA00;">:</span><span style="color: #cc66cc;">0</span> <span style="color: #933;">0.5em</span><span style="color: #00AA00;">;</span>
        <span style="color: #000000; font-weight: bold;">box-shadow</span><span style="color: #00AA00;">:</span> <span style="color: #933;">0px</span> <span style="color: #933;">1px</span> <span style="color: #933;">1px</span> <span style="color: #cc00cc;">#333</span><span style="color: #00AA00;">;</span>
        <span style="color: #000000; font-weight: bold;">text-shadow</span><span style="color: #00AA00;">:</span> <span style="color: #cc66cc;">0</span> <span style="color: #933;">-1px</span> <span style="color: #cc66cc;">0</span> <span style="color: #cc00cc;">#333</span><span style="color: #00AA00;">;</span>
    <span style="color: #00AA00;">&#125;</span></pre></td></tr></table><p class="theCode" style="display:none;">sup {
        font-family: Arial;
        font-size: 0.5em;
        color:#FFF;
        background-color: #333;
        display: inline-block;
        border-radius:0.25em;
        /* reset text-indent */
        text-indent: 0;
        padding:0 0.5em;
        box-shadow: 0px 1px 1px #333;
        text-shadow: 0 -1px 0 #333;
    }</p></div>
    ";}
categories:
  - 代码卷轴
tags:
  - epub
  - ibooks
  - python

---
网上搜到一些国学典籍的 [EPUB][1] 版，虽有古人的注解，但正文和注解混排在一起，当我只想迅速读正文的时候比较碍眼。于是研究了一下 EPUB3 中有关脚注（footnote）的规格定义，写了一个 Python 脚本[把所有混在正文中的脚注全部改写成了弹出窗口样式][2]，在 iBooks 里测试通过，略记一笔。
  
<!--more-->

### 什么是EPUB弹出窗口式脚注

弹出式脚注是 EPUB3 推出的，简单的说就是正文中加一个链接锚点，对应一个脚注模块，点击链接的时候，脚注内容会直接以弹出窗口的形式显示出来。这样就省去了页面跳转这个步骤，更加方便阅读。

一图胜千言，下图是脚本处理后的《<a rel="nofollow" href="http://yun.baidu.com/pcloud/album/file?album_id=725645255657617385&#038;uk=2835490832&#038;fsid=2240115363" title="《三国志》裴松之注 繁体EPUB" target="_blank">三国志</a>》在 iPad 版 iBooks 下的效果。（原本是像[日文电子书那样的竖排EPUB][3]，我把 CSS 里和竖排相关的定义注释掉了）

<img src="http://digglife.qiniudn.com/wp-content/uploads/2014/10/epub-pop-up-footnote.png" alt="三国志 EPUB 弹出窗口式脚注" width="600" height="800" class="alignnone size-full wp-image-3910" />

### 如何实现EPUB弹出窗口式脚注

要实现这种效果，有三个注意点。

  1. 正文中的链接锚点。
<pre lang='html'><p>
  太祖武皇帝，沛國譙人也，姓曹，諱操，字孟德，漢相國參之後。
      <a epub:type="noteref" href="#fn1">
          <sup>1</sup>
      </a>
  桓帝世，曹騰為中常侍大長秋，封費亭侯。
  ......
  
</p>
</pre>

  2. 脚注 aside 模块。
<pre lang='html'>&lt;aside epub:type="footnote" id="fn1">
〔曹瞞傳曰：太祖一名吉利，小字阿瞞。王沈魏書曰：其先出於黃帝。當高陽世，陸終之子曰安，是為曹姓。周武王克殷，存先世之後，封曹俠於邾。春秋之世，與於盟會，逮至戰國，為楚所滅。子孫分流，或家於沛。漢高祖之起，曹參以功封平陽侯，世襲爵士，絶而復紹，至今適嗣國於容城。〕
&lt;/aside>
</pre>

在 iBooks 下，如果 `epub:type` 属性的值为 `footnote` ，这个 `aside` 会默认隐藏。只有对应的链接被点击时，其内容才会在弹出窗口中显示。

  3. epub 命名空间（namespace）。
上面两处都有一个共同的属性名，`epub:type`。一般 EPUB 文档都没有定义 epub 这个命名空间，所以满足以上两点之后直接打开会提示 epub 命名空间没有定义。EPUB 定义 namespace 有两种方式，一种是在 CSS 里定义，一种是在内容页的HTML标签里定义。我测试过，iBooks 无法识别 CSS 里定义的 namespace，所以我采用了另外一种方式。

<pre lang='html'>
</pre>
</ol>


<h3>
  用Python脚本处理EPUB的HTML文档
</h3>


<p>
  了解了这些基本概念之后，再来看要处理的对象。原EPUB文档中注解夹杂在正文中，以<code>span</code>标签标记，所以 Python 脚本的基本流程就比较清楚了，这里使用 <a rel="nofollow" href="http://www.crummy.com/software/BeautifulSoup/" title="BeautifulSoup模块主页" target="_blank">BeautifulSoup</a> 来解析并更改 HTML 文档树。
</p>


<ol>
  <li>
    循环读入所有 EPUB 内容文档并解析
  </li>
  
  
  <li>
    给 <code>html</code> 标签加上 epub 命名空间定义
  </li>
  
  
  <li>
    获取 <code>p</code> 标签下的 所有<code>span</code>标签
  </li>
  
  
  <li>
    遍历获取的<code>span</code>标签，取出文本，并以此创建 <code>aside</code> 模块
  </li>
  
  
  <li>
    清除<code>span</code>标签的内容，更改为链接锚点
  </li>
  
</ol>


<p>
  原 EPUB 中的 HTML 文档节选 ：
</p>


<pre lang='html'>


<p>
  太祖武皇帝，沛國譙人也，姓曹，諱操，字孟德，漢相國參之後。
      <span class="zhushi">
  〔曹瞞傳曰：太祖一名吉利，小字阿瞞。王沈魏書曰：其先出於黃帝。當高陽世，陸終之子曰安，是為曹姓。周武王克殷，存先世之後，封曹俠於邾。春秋之世，與於盟會，逮至戰國，為楚所滅。子孫分流，或家於沛。漢高祖之起，曹參以功封平陽侯，世襲爵士，絶而復紹，至今適嗣國於容城。〕
      </span>
  桓帝世，曹騰為中常侍大長秋，封費亭侯。
  ......
  
</p>
</pre>


<p>
  在 OS X 版 iBooks 中的显示效果，正文注释混排。
</p>


<p>
  <img src="http://digglife.qiniudn.com/wp-content/uploads/2014/10/epub-original-footnote.png" alt="三国志 EPUB 正文脚注混排" width="563" height="841" class="alignnone size-full wp-image-3909" />
</p>


<p>
  详细处理方式见下面的 Python 代码 ：
</p>


<pre lang='python'>
#!/usr/bin/python
# -*- coding: utf-8 -*-

from bs4 import BeautifulSoup
import os

epub_content_path = '/Users/erichu/dev/guoxue/sanguo.epub/OEBPS/Text'

for f in os.listdir(epub_content_path):
    html = os.path.join(epub_content_path,f)
    print html
    doc = open(html,'rb')
    soup = BeautifulSoup(doc)

    #如果没有HTML标签里没有定义epub namespace，则加上
    if not 'xmlns:epub' in soup.html.attrs:
        soup.html['xmlns:epub'] = "http://www.idpf.org/2007/ops"

    #没有使用soup.find_all('span')是为了略过<span>中内嵌<span>的情况
    notes = soup.select('p > span')

    #如果没有找到span标签，进入下一个循环
    if not notes:
        continue
    #反序循环 notes 列表
    for n in range(len(notes)-1, -1, -1):
        #n是列表index，number是实际注释序号
        note = notes[n]
        number = n+1

        footnote = soup.new_tag('aside')
        footnote['epub:type'] = 'footnote'
        footnote['id'] = 'fn%d' % number
        footnote.string = note.get_text()
        #为了保证aside模块是按数字顺序逐一插入到段落之后，所以反序读取notes列表
        note.parent.insert_after(footnote)

        note.clear()
        note.name = "a"
        del note['class']
        note['epub:type'] = 'noteref'
        note['href'] = '#fn%d' % number
        sup = soup.new_tag('sup')
        sup.string = str(number)
        note.append(sup)

    #print soup.prettify()
    doc.close()
    doc = open(html,'wb')
    doc.write(str(soup))
    doc.close()
</pre>


<h3>
  注释锚点的美化
</h3>


<p>
  为了让链接锚点看起来美观一点，我顺手在CSS里给<code>sup</code>添加了几个定义。其中 <code>text-indent</code>是为了重置原CSS代码中 <code>p</code> 标签中的定义，其他的就没什么好说的了。
</p>


<pre lang='css'>
sup {
    font-family: Arial;
    font-size: 0.5em;
    color:#FFF;
    background-color: #333;
    display: inline-block;
    border-radius:0.25em;
    /* reset text-indent */
    text-indent: 0;
    padding:0 0.5em;
    box-shadow: 0px 1px 1px #333;
    text-shadow: 0 -1px 0 #333;
}
</pre>


<p>
  其实在 epub 的 CSS 里定义颜色是一件不太好的事，以 iBooks 为例，主题分纯白、棕褐、夜间三种模式，如果 hardcode 颜色，主题变更时颜色不随之变化就会很难看。不过 iBooks 也似乎没有提供一个办法来解决这种矛盾，所以作罢。
</p>


<h3>
  iBooks 对 EPUB3 标准的支持
</h3>


<p>
  iBooks 对 EPUB3 的支持也并不完全，除了上文提到的CSS命名空间之外，<a rel="nofollow" href="http://www.idpf.org/accessibility/guidelines/content/semantics/separation.php" title="EPUB aside css 样式" target="_blank"><code>aside</code>的 CSS 样式</a> iBooks 也不支持，此外还有<a rel="nofollow" href="http://www.zdnet.com/blog/bott/how-apple-is-sabotaging-an-open-standard-for-digital-books/4378" title="How Apple is sabotaging an open standard for digital books" target="_blank">很多槽点</a>。好像这也是苹果的一贯风格——把现有的处于上升趋势的技术拿来为我所用，然后搞一个私有的变种出来，至于标准，就随便随便啦。
</p>


<p>
  苹果现在对 iBooks 似乎也不是很上心了，可能在电子出版方面遇到的阻力很大，没有帮主的现实扭曲立场，在可见的未来也不太可能复制当年在音乐出版上的成功，于是 iBooks 的臭虫一堆也没人修复，新功能也不见有什么添加，似乎已经很久没有更新了。
</p>


<p>
  可惜现在网上流传的四书五经、二十四史之类的 EPUB 制作良莠不齐，HTML定义也不尽相同，所以没法弄一个通用的脚本出来，只能见招拆招。
</p>

 [1]: https://www.digglife.net/articles/tag/epub "DiggLife EPUB相关文章"
 [2]: https://www.digglife.net/articles/epub-pop-up-footnote.html "EPUB弹出窗口式脚注"
 [3]: https://www.digglife.net/articles/aozora-text-vertical-layout-epub.html "青空文库格式日文电子书转EPUB"