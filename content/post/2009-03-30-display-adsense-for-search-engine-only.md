---
title: 只针对搜索引擎显示Adsense广告
author: 摩摩诘
type: post
date: 2009-03-30T14:33:42+00:00
excerpt: 针对搜索引擎显示Adsense广告是一个很古老的话题，其目的是为了减少无效展示，提高eCPM，也就是所谓的有效每千次展示的费用。
url: /articles/display-adsense-for-search-engine-only.html
syntaxhighlighter_encoded:
  - 1
index_image:
  - https://www.digglife.net/wp-content/uploads/IndexImage/adsense.gif
bot_views:
  - 3046
views:
  - 1895
duoshuo_thread_id:
  - 1154125469839262137
wp-syntax-cache-content:
  - |
    a:3:{i:1;s:2062:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="php" style="font-family:monospace;"><span style="color: #000000; font-weight: bold;">&lt;?php</span>
    <span style="color: #000088;">$referer</span> <span style="color: #339933;">=</span> <span style="color: #000088;">$_SERVER</span><span style="color: #009900;">&#91;</span><span style="color: #0000ff;">'HTTP_REFERER'</span><span style="color: #009900;">&#93;</span><span style="color: #339933;">;</span>
    <span style="color: #000088;">$adsense</span> <span style="color: #339933;">=</span> <span style="color: #339933;">&lt;&lt;</span>ad
    你可以把ADsense的代码
    复制到我的位置
    ad<span style="color: #339933;">;</span> <span style="color: #666666; font-style: italic;">//Adsense代码赋值给$adsense</span>
    <span style="color: #b1b100;">if</span><span style="color: #009900;">&#40;</span><span style="color: #990000;">strpos</span><span style="color: #009900;">&#40;</span><span style="color: #000088;">$referer</span><span style="color: #339933;">,</span><span style="color: #0000ff;">'digglife.cn'</span><span style="color: #009900;">&#41;</span> <span style="color: #339933;">==</span> <span style="color: #009900; font-weight: bold;">false</span><span style="color: #009900;">&#41;</span><span style="color: #009900;">&#123;</span>
    <span style="color: #b1b100;">echo</span> <span style="color: #000088;">$adsense</span><span style="color: #339933;">;</span>
    <span style="color: #009900;">&#125;</span><span style="color: #666666; font-style: italic;">//判断$referer中是否含有digglife.cn,无则输出$adsense</span>
    <span style="color: #000000; font-weight: bold;">?&gt;</span></pre></td></tr></table><p class="theCode" style="display:none;">&lt;?php
    $referer = $_SERVER['HTTP_REFERER'];
    $adsense = &lt;&lt;ad
    你可以把ADsense的代码
    复制到我的位置
    ad; //Adsense代码赋值给$adsense
    if(strpos($referer,'digglife.cn') == false){
    echo $adsense;
    }//判断$referer中是否含有digglife.cn,无则输出$adsense
    ?&gt;</p></div>
    ";i:2;s:3157:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="php" style="font-family:monospace;"><span style="color: #000000; font-weight: bold;">&lt;?php</span>
    <span style="color: #000088;">$referer</span> <span style="color: #339933;">=</span> <span style="color: #000088;">$_SERVER</span><span style="color: #009900;">&#91;</span><span style="color: #0000ff;">'HTTP_REFERER'</span><span style="color: #009900;">&#93;</span><span style="color: #339933;">;</span>
    <span style="color: #000088;">$adsense</span> <span style="color: #339933;">=</span> <span style="color: #339933;">&lt;&lt;</span>AD
    adsense的代码
    AD<span style="color: #339933;">;</span>
    <span style="color: #b1b100;">if</span><span style="color: #009900;">&#40;</span><span style="color: #990000;">strpos</span><span style="color: #009900;">&#40;</span><span style="color: #000088;">$referer</span><span style="color: #339933;">,</span><span style="color: #0000ff;">'google'</span><span style="color: #009900;">&#41;</span> <span style="color: #339933;">!==</span> <span style="color: #009900; font-weight: bold;">false</span><span style="color: #009900;">&#41;</span><span style="color: #009900;">&#123;</span>
    <span style="color: #b1b100;">echo</span> <span style="color: #000088;">$adsense</span><span style="color: #339933;">;</span>
    <span style="color: #009900;">&#125;</span><span style="color: #b1b100;">elseif</span><span style="color: #009900;">&#40;</span><span style="color: #990000;">strpos</span><span style="color: #009900;">&#40;</span><span style="color: #000088;">$referer</span><span style="color: #339933;">,</span><span style="color: #0000ff;">'baidu'</span><span style="color: #009900;">&#41;</span> <span style="color: #339933;">!==</span> <span style="color: #009900; font-weight: bold;">false</span><span style="color: #009900;">&#41;</span><span style="color: #009900;">&#123;</span>
    <span style="color: #b1b100;">echo</span> <span style="color: #000088;">$adsense</span><span style="color: #339933;">;</span>
    <span style="color: #009900;">&#125;</span><span style="color: #b1b100;">elseif</span><span style="color: #009900;">&#40;</span><span style="color: #990000;">strpos</span><span style="color: #009900;">&#40;</span><span style="color: #000088;">$referer</span><span style="color: #339933;">,</span><span style="color: #0000ff;">'soso'</span><span style="color: #009900;">&#41;</span> <span style="color: #339933;">!==</span> <span style="color: #009900; font-weight: bold;">false</span><span style="color: #009900;">&#41;</span><span style="color: #009900;">&#123;</span>
    <span style="color: #b1b100;">echo</span> <span style="color: #000088;">$adsense</span><span style="color: #339933;">;</span>
    ｝
    <span style="color: #000000; font-weight: bold;">?&gt;</span></pre></td></tr></table><p class="theCode" style="display:none;">&lt;?php
    $referer = $_SERVER['HTTP_REFERER'];
    $adsense = &lt;&lt;AD
    adsense的代码
    AD;
    if(strpos($referer,'google') !== false){
    echo $adsense;
    }elseif(strpos($referer,'baidu') !== false){
    echo $adsense;
    }elseif(strpos($referer,'soso') !== false){
    echo $adsense;
    ｝
    ?&gt;</p></div>
    ";i:3;s:2752:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="php" style="font-family:monospace;"><span style="color: #000000; font-weight: bold;">&lt;?php</span>
    <span style="color: #000088;">$referer</span> <span style="color: #339933;">=</span> <span style="color: #000088;">$_SERVER</span><span style="color: #009900;">&#91;</span><span style="color: #0000ff;">'HTTP_REFERER'</span><span style="color: #009900;">&#93;</span><span style="color: #339933;">;</span>
    <span style="color: #000088;">$se</span> <span style="color: #339933;">=</span> <span style="color: #990000;">array</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'google.com/search?'</span><span style="color: #339933;">,</span> <span style="color: #0000ff;">'baidu.com/s?'</span><span style="color: #339933;">,</span> <span style="color: #0000ff;">'soso.com/q?'</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    <span style="color: #000088;">$adsense</span> <span style="color: #339933;">=</span> <span style="color: #339933;">&lt;&lt;</span>AD
    adsense代码
    AD<span style="color: #339933;">;</span>
    <span style="color: #b1b100;">foreach</span> <span style="color: #009900;">&#40;</span><span style="color: #000088;">$se</span> <span style="color: #b1b100;">as</span> <span style="color: #000088;">$source</span><span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span><span style="color: #666666; font-style: italic;">//将se数组中的每一个值逐一赋给$source</span>
    <span style="color: #b1b100;">if</span><span style="color: #009900;">&#40;</span><span style="color: #990000;">strpos</span><span style="color: #009900;">&#40;</span><span style="color: #000088;">$referer</span><span style="color: #339933;">,</span><span style="color: #000088;">$source</span><span style="color: #009900;">&#41;</span> <span style="color: #339933;">!==</span> <span style="color: #009900; font-weight: bold;">false</span><span style="color: #009900;">&#41;</span><span style="color: #009900;">&#123;</span>
    <span style="color: #b1b100;">echo</span> <span style="color: #000088;">$adsense</span><span style="color: #339933;">;</span>
    <span style="color: #009900;">&#125;</span>
    <span style="color: #009900;">&#125;</span>
    <span style="color: #000000; font-weight: bold;">?&gt;</span>;</pre></td></tr></table><p class="theCode" style="display:none;">&lt;?php
    $referer = $_SERVER['HTTP_REFERER'];
    $se = array('google.com/search?', 'baidu.com/s?', 'soso.com/q?');
    $adsense = &lt;&lt;AD
    adsense代码
    AD;
    foreach ($se as $source) {//将se数组中的每一个值逐一赋给$source
    if(strpos($referer,$source) !== false){
    echo $adsense;
    }
    }
    ?&gt;;</p></div>
    ";}
categories:
  - 谷歌相关
tags:
  - adsense
  - google
  - php

---
针对搜索引擎显示[Adsense][1]广告是一个很古老的话题，其目的是为了减少无效展示，提高eCPM，也就是所谓的有效每千次展示的费用。江湖上传言eCPM高了，Adsense机器人会自动匹配高单价的广告到你的网页，所以在点击率一定的情况下，提高eCPM是是一种有效提高广告收入的办法。

网上流传的有三种办法，原理都是一致的，只是有的简单有的复杂，有的功能强有的效率高。曾经一度使用<a title="根据来源显示特定内容 " href="http://ooxx.me/server-http-referer.orz" target="_blank">大猫老湿的习作</a>，但是后来发现还需要继续缩小范围，所以就自己研究了一下。

<!--more-->

首先看看原始代码：

<pre lang="php"><?php
$referer = $_SERVER['HTTP_REFERER'];
$adsense = <<ad
你可以把ADsense的代码
复制到我的位置
ad; //Adsense代码赋值给$adsense
if(strpos($referer,'digglife.cn') == false){
echo $adsense;
}//判断$referer中是否含有digglife.cn,无则输出$adsense
?>
</pre>

我虽然没学过PHP，但是这些代码还是很容易懂的，上面的注解尽管不专业，但是意思上不会有差错。Strpos本来是寻找字符串中某字符最先出现处，有则返回整数值，但是因为如果没有就返回false，所以这里用着刚刚好。

这段代码采用的是一种排除法，只要不是直接进入digglife的，一律显示广告。但是我通过Google Analystic分析的结果是，99%的收入来自谷歌，百度和搜搜，所以只想针对这三个搜索引擎显示广告，这样只能通过正面判断。

当然，可以如下这么写，还是大猫的家庭作业：

<pre lang="php"><?php
$referer = $_SERVER['HTTP_REFERER'];
$adsense = <<AD
adsense的代码
AD;
if(strpos($referer,'google') !== false){
echo $adsense;
}elseif(strpos($referer,'baidu') !== false){
echo $adsense;
}elseif(strpos($referer,'soso') !== false){
echo $adsense;
｝
?>
</pre>

但是适合对不同的搜索引擎显示一样的内容，如果内容相同，就可以利用foreach循环语句将其简化。另外，反链中包含有&#8221;google&#8221;和&#8221;baidu&#8221;并不代表一定来自这两个搜索引擎的搜索结果页，来自Greader和百度空间之类的访客也会看到广 告，如果觉得这个不爽，可以将&#8217;google&#8217;改为&#8217;google.com/search?&#8217;，&#8221;baidu&#8221;改为&#8217;baidu.com/s?&#8217;，这样更加精确。

<pre lang="php"><?php
$referer = $_SERVER['HTTP_REFERER'];
$se = array('google.com/search?', 'baidu.com/s?', 'soso.com/q?');
$adsense = <<AD
adsense代码
AD;
foreach ($se as $source) {//将se数组中的每一个值逐一赋给$source
if(strpos($referer,$source) !== false){
echo $adsense;
}
}
?>;
</pre>

不过Foreach这个方法要将数组里面的每一个值都执行一遍，也就是所谓的遍历，执行效率从理论上说要比上面那个低一点。

PHP看起来好像很牛逼的样子，啥时候俺也来学学。

 [1]: https://www.digglife.net/tag/adsense "adsense"