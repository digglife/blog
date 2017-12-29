---
title: 如何让程序自动绕过百度云加速的浏览器安全检查
author: 摩摩诘
type: post
date: 2016-03-24T13:02:49+00:00
excerpt: 最近写了一个Perl脚本自动调用迅雷远程下载电影，目标电影站是赫赫有名的 MP4BA。本来运行得挺好，每次有符合条件的好电影发布，脚本就会自动通过调用运行在Raspberry Pi上的迅雷远程将其下载到本地。但是今天程序一直报 503 错误，后来发现是百度云加速的浏览器安全检查在作祟，用户有时需要通过一次校检才能正常访问网站
url: /articles/how-to-cheat-baidu-yunjiasu.html
index_image:
  - https://www.digglife.net/wp-content/uploads/2016/03/break-s.jpg
categories:
  - 代码卷轴
tags:
  - perl
  - 爬虫
  - 百度云
  - 迅雷

---
最近写了一个Perl脚本自动调用迅雷远程下载电影，目标电影站是赫赫有名的 MP4BA。本来运行得挺好，每次有符合条件的电影发布，脚本就会自动通过调用运行在 Raspberry Pi 上的迅雷远程将其下载到本地。但是今天程序一直报 503 错误，后来发现是百度云加速的浏览器安全检查在作祟，用户有时需要通过一次校检才能正常访问网站。我估计这种防护，本身也是为了防止各种非正常机器人的侵袭？

<!--more-->

<img src="http://digglife.qiniudn.com/wp-content/uploads/2016/03/break-500x316.jpg" alt="让程序绕过百度运价速浏览器安全检查" width="500" height="316" />

这个安全检查的原理其实很简单。用户在访问网站的时候，服务器首先发回一个返回码为 503 的页面，核心是页面中一个隐藏的 Form 和一段 Javascript 代码，后者负责生成 form 中的某一个输入值，然后提交，服务器对提交的各项值进行校检，通过则跳转到正常网站，并生成一个 Cookie 保证后续正常访问。因为有一个关键的校检值是由 Javascript 生成的，所以能一定程度上能保证访问者是通过正常的浏览器访问的，而不是机器程序。

下面是一个例子，注意高亮的代码。`JdcdXuQ` 这个对象名，以及属性 `BKdYXrXP` 都是随机生成的，后面的一系列相关的计算语句也是随机生成的，所以 `jschl-answer` 的值，是完全随机的。

```javascript
  (function(){
    var a = function() {try{return !!window.addEventListener} catch(e) {return !1} },
    b = function(b, c) {a() ? document.addEventListener("DOMContentLoaded", b, c) : document.attachEvent("onreadystatechange", b)};
    b(function(){
      var a = document.getElementById('yjs-content');a.style.display = 'block';
      setTimeout(function(){
        var t,r,a,f, JdcdXuQ={"BKdYXrXP":+((!+[]+!![]+!![]+[])+(!+[]+!![]+!![]))};
        t = document.createElement('div');
        t.innerHTML="<a href='/'>x</a>";
        t = t.firstChild.href;r = t.match(/https?:\/\//)[0];
        t = t.substr(r.length); t = t.substr(0,t.length-1);
        a = document.getElementById('jschl-answer');
        f = document.getElementById('challenge-form');
        ;JdcdXuQ.BKdYXrXP-=+((!+[]+!![]+[])+(!+[]+!![]+!![]+!![]+!![]+!![]));JdcdXuQ.BKdYXrXP-=+((+!![]+[])+(!+[]+!![]));JdcdXuQ.BKdYXrXP*=+((!+[]+!![]+[])+(!+[]+!![]+!![]+!![]+!![]+!![]+!![]+!![]));JdcdXuQ.BKdYXrXP-=+((+!![]+[])+(!+[]+!![]));JdcdXuQ.BKdYXrXP-=+((!+[]+!![]+[])+(!+[]+!![]+!![]+!![]+!![]+!![]+!![]+!![]));JdcdXuQ.BKdYXrXP+=!+[]+!![]+!![]+!![];JdcdXuQ.BKdYXrXP-=+((!+[]+!![]+[])+(!+[]+!![]+!![]+!![]+!![]+!![]+!![]+!![]));JdcdXuQ.BKdYXrXP+=+((!+[]+!![]+!![]+!![]+[])+(+!![]));a.value = parseInt(JdcdXuQ.BKdYXrXP, 10) + t.length;
        f.submit();
      }, 4000);
    }, false);
  })();
  //
```

上面的JS，提交的是下面这一个Form。可以看到 `jschl_vc` 和 `pass` 本身就有 value，唯有 `jschl-answer` 没有 value 属性。

那么现在的问题就是，如何让 Perl 能够将相关的 JS 代码截取出来，然后运行得出和JS一样的结果。

大 CPAN 上有一个处于 Alpha 阶段的模块，名叫<a href="https://metacpan.org/pod/JE" target="_blank">JE</a>，也就是 Javascript Engine 的缩写，是一个用纯 Perl 实现的 JS 引擎，好流弊，正符合我的需要。

解析校检链接的方法如下。基本思路就是把和值计算相关的语句都用正则撷取出来，然后使用JE执行。

```perl
sub get_baidu_yjs_check_url {
    my $site_url = shift;
    my $content = shift;

    use JE;
    use URI;

    my $uri = URI->new($site_url);
    my $je = new JE;
    my $tree = HTML::TreeBuilder->new;
    $tree->parse($content);
    my $js = $tree->look_down("_tag", "script");
    $js = $js->as_HTML;
    $js =~ s/^\&lt;\/?script.*|^\s+\/\/.*//gm;
    my ($first_assignment, $object, $key) =
        $js =~ /var t,r,a,f, ((\w+)\=\{"(\w+)\"\:.*)/;
    my ($multiple_caculation) = $js =~ /;(.*;)a\.value/;

    #print $first_assignment . $multiple_caculation . "\n";
    my $final_number = $je->eval($first_assignment . $multiple_caculation);
    my $answer = $final_number + length($uri->host);
    my $form = $tree->look_down("_tag", "form");
    my $jschk_url = $site_url . $form->attr('action');
    my @inputs = $form->look_down("_tag", "input");
    my %query;
    for my $input ( @inputs ) {
        $query{$input->attr("name")} = $input->attr("value");
    }
    $query{'jschl_answer'} = $answer;
    #print Dumper(\%query);
    my @params;
    for ( keys %query ) {
        push @params, join('=', $_, $query{$_});
    }
    $jschk_url .= '?' . join('&', @params);
    return $jschk_url;
}
```

有了这个链接，后续只用读取后保存cookie，然后继续访问原网站就OK了。

详情可见 Github Repo：<a href="https://github.com/digglife/tienlo" target="_blank">tienlo</a>。

