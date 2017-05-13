---
title: 扯淡：计算数组元素出现次数
author: 摩摩诘
type: post
date: 2015-07-03T15:36:03+00:00
excerpt: '给定长度为n（比如15）的整数数组，求出所有出现次数大于n/3的整数。比如[3, 7, 3, 6, 3, 6, 3, 6, 7, 3, 53, 6, 3, 6, 6]。'
url: /articles/array-count.html
views:
  - 496
duoshuo_thread_id:
  - 1154125469839262206
index_image:
  - https://www.digglife.net/wp-content/uploads/2016/05/array.jpg
post_views_count:
  - 1
wp-syntax-cache-content:
  - |
    a:4:{i:1;s:2018:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="python" style="font-family:monospace;"><span style="color: black;">&#91;</span>k <span style="color: #ff7700;font-weight:bold;">for</span> k<span style="color: #66cc66;">,</span>v <span style="color: #ff7700;font-weight:bold;">in</span> <span style="color: #008000;">reduce</span><span style="color: black;">&#40;</span><span style="color: #ff7700;font-weight:bold;">lambda</span> acc<span style="color: #66cc66;">,</span>v: <span style="color: black;">&#40;</span>acc.<span style="color: #0000cd;">__setitem__</span><span style="color: black;">&#40;</span>v<span style="color: #66cc66;">,</span>acc.<span style="color: black;">get</span><span style="color: black;">&#40;</span>v<span style="color: #66cc66;">,</span><span style="color: #ff4500;">0</span><span style="color: black;">&#41;</span>+<span style="color: #ff4500;">1</span><span style="color: black;">&#41;</span><span style="color: #66cc66;">,</span>acc<span style="color: black;">&#41;</span><span style="color: black;">&#91;</span>-<span style="color: #ff4500;">1</span><span style="color: black;">&#93;</span><span style="color: #66cc66;">,</span> l<span style="color: #66cc66;">,</span> <span style="color: #008000;">dict</span><span style="color: black;">&#40;</span><span style="color: black;">&#41;</span><span style="color: black;">&#41;</span>.<span style="color: black;">items</span><span style="color: black;">&#40;</span><span style="color: black;">&#41;</span> <span style="color: #ff7700;font-weight:bold;">if</span> v<span style="color: #66cc66;">&gt;</span><span style="color: #008000;">len</span><span style="color: black;">&#40;</span>l<span style="color: black;">&#41;</span>/<span style="color: #ff4500;">3</span><span style="color: black;">&#93;</span></pre></td></tr></table><p class="theCode" style="display:none;">[k for k,v in reduce(lambda acc,v: (acc.__setitem__(v,acc.get(v,0)+1),acc)[-1], l, dict()).items() if v&gt;len(l)/3]</p></div>
    ";i:2;s:2630:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="python" style="font-family:monospace;"><span style="color: #ff7700;font-weight:bold;">import</span> <span style="color: #dc143c;">collections</span>
    a <span style="color: #66cc66;">=</span> <span style="color: black;">&#91;</span><span style="color: #ff4500;">3</span><span style="color: #66cc66;">,</span> <span style="color: #ff4500;">7</span><span style="color: #66cc66;">,</span> <span style="color: #ff4500;">3</span><span style="color: #66cc66;">,</span> <span style="color: #ff4500;">6</span><span style="color: #66cc66;">,</span> <span style="color: #ff4500;">3</span><span style="color: #66cc66;">,</span> <span style="color: #ff4500;">6</span><span style="color: #66cc66;">,</span> <span style="color: #ff4500;">3</span><span style="color: #66cc66;">,</span> <span style="color: #ff4500;">6</span><span style="color: #66cc66;">,</span> <span style="color: #ff4500;">7</span><span style="color: #66cc66;">,</span> <span style="color: #ff4500;">3</span><span style="color: #66cc66;">,</span> <span style="color: #ff4500;">53</span><span style="color: #66cc66;">,</span> <span style="color: #ff4500;">6</span><span style="color: #66cc66;">,</span> <span style="color: #ff4500;">3</span><span style="color: #66cc66;">,</span> <span style="color: #ff4500;">6</span><span style="color: #66cc66;">,</span> <span style="color: #ff4500;">6</span><span style="color: black;">&#93;</span>
    c <span style="color: #66cc66;">=</span> <span style="color: #dc143c;">collections</span>.<span style="color: black;">Counter</span><span style="color: black;">&#40;</span>a<span style="color: black;">&#41;</span>
    result <span style="color: #66cc66;">=</span> <span style="color: black;">&#91;</span>i <span style="color: #ff7700;font-weight:bold;">for</span> i <span style="color: #ff7700;font-weight:bold;">in</span> c.<span style="color: black;">keys</span><span style="color: black;">&#40;</span><span style="color: black;">&#41;</span> <span style="color: #ff7700;font-weight:bold;">if</span> c<span style="color: black;">&#91;</span>i<span style="color: black;">&#93;</span> <span style="color: #66cc66;">&gt;</span> <span style="color: #008000;">len</span><span style="color: black;">&#40;</span>a<span style="color: black;">&#41;</span>/<span style="color: #ff4500;">3</span><span style="color: black;">&#93;</span></pre></td></tr></table><p class="theCode" style="display:none;">import collections
    a = [3, 7, 3, 6, 3, 6, 3, 6, 7, 3, 53, 6, 3, 6, 6]
    c = collections.Counter(a)
    result = [i for i in c.keys() if c[i] &gt; len(a)/3]</p></div>
    ";i:3;s:2856:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="perl" style="font-family:monospace;"><span style="color: #0000ff;">@a</span> <span style="color: #339933;">=</span> <span style="color: #009900;">&#40;</span><span style="color: #cc66cc;">3</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">7</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">3</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">6</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">3</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">6</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">3</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">6</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">7</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">3</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">53</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">6</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">3</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">6</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">6</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    <span style="color: #666666; font-style: italic;"># 第一次 grep 找出符合条件的整数，第二次 grep 去重</span>
    <span style="color: #0000ff;">@result</span> <span style="color: #339933;">=</span> <span style="color: #000066;">grep</span> <span style="color: #009900;">&#123;</span> <span style="color: #339933;">!</span><span style="color: #0000ff;">$j</span><span style="color: #009900;">&#91;</span><span style="color: #0000ff;">$_</span><span style="color: #009900;">&#93;</span><span style="color: #339933;">++</span> <span style="color: #009900;">&#125;</span> <span style="color: #000066;">grep</span> <span style="color: #009900;">&#123;</span> <span style="color: #339933;">++</span><span style="color: #0000ff;">$i</span><span style="color: #009900;">&#123;</span><span style="color: #0000ff;">$_</span><span style="color: #009900;">&#125;</span> <span style="color: #339933;">&gt;</span> <span style="color: #0000ff;">@a</span><span style="color: #339933;">/</span><span style="color: #cc66cc;">3</span> <span style="color: #009900;">&#125;</span> <span style="color: #0000ff;">@a</span><span style="color: #339933;">;</span></pre></td></tr></table><p class="theCode" style="display:none;">@a = (3, 7, 3, 6, 3, 6, 3, 6, 7, 3, 53, 6, 3, 6, 6);
    # 第一次 grep 找出符合条件的整数，第二次 grep 去重
    @result = grep { !$j[$_]++ } grep { ++$i{$_} &gt; @a/3 } @a;</p></div>
    ";i:4;s:2620:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="perl" style="font-family:monospace;"><span style="color: #0000ff;">@a</span> <span style="color: #339933;">=</span> <span style="color: #009900;">&#40;</span><span style="color: #cc66cc;">3</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">7</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">3</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">6</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">3</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">6</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">3</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">6</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">7</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">3</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">53</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">6</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">3</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">6</span><span style="color: #339933;">,</span> <span style="color: #cc66cc;">6</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    <span style="color: #0000ff;">$h</span><span style="color: #009900;">&#123;</span><span style="color: #0000ff;">$_</span><span style="color: #009900;">&#125;</span><span style="color: #339933;">++</span> <span style="color: #b1b100;">for</span> <span style="color: #0000ff;">@a</span><span style="color: #339933;">;</span>
    <span style="color: #0000ff;">$results</span> <span style="color: #339933;">=</span> <span style="color: #000066;">grep</span> <span style="color: #009900;">&#123;</span> <span style="color: #0000ff;">$h</span><span style="color: #009900;">&#123;</span><span style="color: #0000ff;">$_</span><span style="color: #009900;">&#125;</span> <span style="color: #339933;">&gt;</span> <span style="color: #0000ff;">@a</span><span style="color: #339933;">/</span><span style="color: #cc66cc;">3</span> <span style="color: #009900;">&#125;</span> <span style="color: #000066;">keys</span> <span style="color: #0000ff;">%h</span><span style="color: #339933;">;</span></pre></td></tr></table><p class="theCode" style="display:none;">@a = (3, 7, 3, 6, 3, 6, 3, 6, 7, 3, 53, 6, 3, 6, 6);
    $h{$_}++ for @a;
    $results = grep { $h{$_} &gt; @a/3 } keys %h;</p></div>
    ";}
categories:
  - 代码卷轴
tags:
  - perl
  - python

---
看到一个编码题目，描述是，给定长度为n（比如15）的整数数组，求出所有出现次数大于n/3的整数。比如[3, 7, 3, 6, 3, 6, 3, 6, 7, 3, 53, 6, 3, 6, 6]。

然后当然有各种语言的答案，其中有个人写了个 Python 的代码，比较长，而且复杂，于是被人嘲讽Python丑哭。

<!--more-->

<pre lang='python'>[k for k,v in reduce(lambda acc,v: (acc.__setitem__(v,acc.get(v,0)+1),acc)[-1], l, dict()).items() if v>len(l)/3] 
</pre>

这种浆糊代码显然是一点都不 Pythonic 的。我觉得没理由 Python 解决这种小问题会这么复杂，何况这种 iterable 对象的次数统计，用 Python 的 <a href="https://docs.python.org/2/library/collections.html" target="_blank">collections</a> 库刚刚好，何苦自己瞎折腾。

<pre lang='python'>import collections
a = [3, 7, 3, 6, 3, 6, 3, 6, 7, 3, 53, 6, 3, 6, 6]
c = collections.Counter(a)
result = [i for i in c.keys() if c[i] > len(a)/3]
</pre>

当然，collections 需要事先 `import` 一下，好像不是那么的能显示 Coder 自己的功夫，但是啊，Python 号称 <a href="https://www.digglife.net/articles/python-urllib.html" target="_blank">Battery Included</a> ，不就是让人充分利用这些内置库吗？

其实看到这个题目，我第一反应是用Perl，一行流：

<pre lang='perl'>@a = (3, 7, 3, 6, 3, 6, 3, 6, 7, 3, 53, 6, 3, 6, 6);
# 第一次 grep 找出符合条件的整数，第二次 grep 去重
@result = grep { !$j[$_]++ } grep { ++$i{$_} > @a/3 } @a;
</pre>

玩一行流，Perl 的优势是极大的。

  1. 变量不用事先声明。
默认不开 strict 模式，直接使用 `%i, %j` 这两个 hash 是没问题的。

  2. 直接使用 hash 不会检查 key 是否存在，所谓 <a href="https://en.wikipedia.org/wiki/Autovivification" target="_blank">autovivification</a>。
虽然 `%i` 这个 hash 里没有事先定义 `@a` 中的任何一个值作为 key，但是也可以直接拿值来计算。这个特性，有好有坏，但是我觉得还是好处居多。

  3. 隐形的类型转换。
比如这里的 `$i{$_}` 值是 `undef` 的时候，自增运算会变成 1。数组变量在 scalar 上下文中自动转换成数组的长度，所以可以直接使用 `@a/3`。

如果某个元素出现的次数远大于n/3，上面的代码在第一次grep的时候会做一些无用的比较，会把这个元素多次过滤出来，所以需要去重。避免这种情况可以使用用类似上面 Python 代码的流程。总之思路都是先创建一个以元素为key，以出现次数为value的hash。

<pre lang='perl'>@a = (3, 7, 3, 6, 3, 6, 3, 6, 7, 3, 53, 6, 3, 6, 6);
$h{$_}++ for @a;
$results = grep { $h{$_} > @a/3 } keys %h;
</pre>

不过我也是无聊，好久不写博客，大半夜竟然发这种东西。