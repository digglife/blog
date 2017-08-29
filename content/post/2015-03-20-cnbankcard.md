---
title: 通过银行卡号解析银行名称和卡别
author: 摩摩诘
type: post
date: 2015-03-20T15:38:46+00:00
excerpt: 前几天在支付宝添加银行卡的时候注意到输完卡号支付宝就自动识别了银行名称，所以用Firefox自带的工具看了一下实现方式，发现支付宝有一个 API 来做这个事情，只要依据固定的格式发送HTTP请求就可以获得JSON格式的结果，除了对应的银行名称代码之外，还有银行卡的类型（储蓄卡/信用卡）。
url: /articles/cnbankcard.html
index_image:
  - https://www.digglife.net/wp-content/uploads/2015/03/bankcard.png
categories:
  - 代码卷轴
tags:
  - python
  - 银行卡

---
前几天在支付宝添加银行卡的时候注意到输完卡号支付宝就自动识别了银行名称，所以用Firefox自带的工具看了一下实现方式，发现支付宝有一个 API 来做这个事情，只要依据固定的格式发送HTTP请求就可以获得JSON格式的结果，除了对应的银行名称代码之外，还有银行卡的类型（储蓄卡/信用卡）。

<!--more-->

<img src="http://digglife.qiniudn.com/wp-content/uploads/2016/05/bank-cards.jpg" alt="各种银行卡" width="468" height="286" class="alignnone size-full wp-image-4062" />

把以下URL中的银行卡卡号替换成需要查询的真实卡号即可。

<pre lang="bash">https://ccdcapi.alipay.com/validateAndCacheCardInfo.json?_input_charset=utf-8&cardNo=银行卡卡号&cardBinCheck=true
</pre>

下面是一个农业银行的例子，当然卡号是假的，只是头6位是农行的BIN码而已。支付宝的这个API并没有使用<a href="http://en.wikipedia.org/wiki/Luhn_algorithm" title="Luhn算法" target="_blank">LUHN算法</a>来验证银行卡是否合法。

<pre lang="bash">zhu@tp430:~/Dev/cnbankcard$ http "https://ccdcapi.alipay.com/validateAndCacheCardInfo.json?_input_charset=utf-8&cardNo=6228430120000000000&cardBinCheck=true"
HTTP/1.1 200 OK
Connection: keep-alive
Content-Language: zh-CN
Content-Length: 101
Content-Type: application/json;charset=GBK
Date: Sun, 08 Mar 2015 15:21:17 GMT
Server: spanner/1.0.6
Set-Cookie: JSESSIONID=CCDE8AA9E2DAEC082A7614734AF729FB; Path=/; HttpOnly
Set-Cookie: JSESSIONID=CCDE8AA9E2DAEC082A7614734AF729FB; Path=; Secure; HttpOnly
Set-Cookie: spanner=dauWw2JHEhbWoKV/zrMf2LLFCxFf8h1G;path=/;secure;
Strict-Transport-Security: max-age=31536000

{
    "bank": "ABC", 
    "cardType": "DC", 
    "key": "6228430120000000000", 
    "messages": [], 
    "stat": "ok", 
    "validated": true
}
</pre>

因为JSON数据里的银行名称是英文代码，所以写了一个 <a href="https://github.com/digglife/cnbankcard/blob/master/parsebanks.py" title="python获取银行代码对应的中文名" target="_blank">Python 脚本</a>从<a href="http://ab.alipay.com/i/yinhang.htm" title="支付宝银行合作伙伴" target="_blank">支付宝的合作银行页面</a>自动获取英文代码对应的中文银行名。

此外，银行的LOGO也可以用过<a href="https://github.com/digglife/cnbankcard#%E9%93%B6%E8%A1%8Clogo%E5%9B%BE%E7%89%87-api" title="银行Logo图片 API" target="_blank">支付宝提供的一个图片API</a>获取。

以上详情我都记录在<a href="https://github.com/digglife/cnbankcard" title="cnbankcard" target="_blank">cnbankcard</a>这个Github Repo里。

其实背后的原理也很简单。一般来说，通过银行卡卡号的前6位BIN码可以得出该银行卡的发卡行，所以只要有一个事先准备好的字典，就能写一个简单的程序来通过银行卡卡号识别银行名称。网上有一些提供银行卡查询的网站，甚至能识别到归属地，部分还提供了收费API。不过既然支付宝有这种不公开的开放API，就不必去花钱了。