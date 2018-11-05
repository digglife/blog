---
title: 吐槽一下 Python 的urllib 和 urllib2
author: 摩摩诘
type: post
date: 2014-10-10T14:37:02+00:00
excerpt: 最近在用 Python 封装一个内部 RESTful API，所以用到 urllib 模块，结果发现连 Request 对象都不支持，那还玩个毛，于是我惊喜地发现还有一个 urllib2，嗯，居然自身就支持 Request，连 httplib 都可以不用了，真好哇，结果发现尼玛竟然只支持 GET/POST，想要发其他 HTTP Request 比如 DELETE/PUT 的话，要不就还是用回 httplib，要不得用一个一点都不符合直觉的 Hack 。
url: /articles/python-urllib.html
index_image:
  - https://www.digglife.net/wp-content/uploads/2014/10/urllib.jpg
views:
  - 559
duoshuo_thread_id:
  - 1154125469839262198
post_views_count:
  - 2
categories:
  - 代码卷轴
tags:
  - perl
  - python

---
最近在用 Python 封装一个内部 RESTful API，所以用到 `urllib` 模块，结果发现连 Request 对象都不支持，那还玩个毛，于是我惊喜地发现还有一个 `urllib2`，嗯，居然自带 Request，连 `httplib` 都可以不用了，真好哇，结果发现尼玛竟然只支持 `GET/POST`，想要发其他 HTTP Request 比如 `DELETE/PUT` 的话，要不就还是用回 `httplib`，要不得用<a rel="nofollow" href="stackoverflow.com/questions/4511598/how-to-make-http-delete-method-using-urllib2" title="How to make HTTP DELETE method using urllib2?" target="_blank">一个一点都不符合直觉的 Hack</a> 。

<!--more-->

另外，从包名来说，照理 `urllib2` 应该是个升级版吧，结果发现有些 urllib 里用得好好的方法比如 `urlquote`、`urlencode` 在 `urllib2` 里又没了。这特么是在逗我？搜了一下发现，原来 Python 2 时代的 Best Practice 是两个模块一起用，呃&#8230;我也承认自己的智商不够，可是这种搞法是不是太乱了点。

<img src="https://www.digglife.net/wp-content/uploads/2014/10/http-request.jpg" alt="吐槽一下 Python 的urllib 和 urllib2" width="600" height="309" class="alignnone size-full wp-image-3919" />

可能也 Python 的开发者觉得这个状况太莫名奇妙，于是 Python 3 重新整合成了唯一的 `urllib`，不过<a rel="nofollow" href="https://docs.python.org/3/library/urllib.html" title="Python 3 的 urllib模块" target="_blank">分出了 4 个支模块</a>。Python 的粉丝们估计觉得这种搞法依然稀烂，简直特么不是给人用的，所以有人自己写了个 <a rel="nofollow" href="http://docs.python-requests.org/en/latest/" title="Python Request模块" target="_blank">requests</a> 模块，口号是 HTTP For Humans ，感觉简直是嘲讽全开啊。

这方面 Perl 就比较鸡贼了，你要玩儿 HTTP 客户端是吧？标准库里没有哦，电池不内置哦，自己去写吧，于是催生出了几乎有标准库地位的 `LWP::UserAgent`、`HTTP::Request` 等，使用起来思路是很清晰的。我在当初用 Perl 封装 API 的时候一点都没觉得复杂。

当然，我也不是说 Python 不好，Python好的地方多了去了，很多第三方库都是神器，何况类似的这种历史包袱从整体上说 Perl 比 Python 还要重，只是无论哪种语言都最常用的那些库，比如文件系统、数据库、HTTP请求等，我在当初学 Perl 都没有这方面的迷惑， 而一个风评比 鬼畜Perl 要简洁优雅的语言（喷 Perl 最多的大概就是 Python 的使用者了），却在这里有些混乱，的确是大出我意料之外&#8230; 所以编程语言语言战争这种事情，真的是很无谓，在什么合适的地方用合适的语言就好了，喷个锤子。

更新：

Perl 自从 `5.13.9` 开始内置了 <a href="https://github.com/chansen/p5-http-tiny" target="_blank">HTTP::Tiny</a> 这个模块，而且 API 比 `LWP` 系的模块要简单直接，所以上文中的 Perl 标准库里没有 HTTP 客户端的话是有问题的。:)
