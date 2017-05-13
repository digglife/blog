---
title: 配置Squid代理Git协议
author: 摩摩诘
type: post
date: 2014-12-19T06:02:07+00:00
excerpt: 本来 squid 默认支持 http 等常见协议，给 git 客户端配置一下 http.proxy 和 https.proxy 也足够了，但是这样每次 clone 的时候就只能使用 https 形式的链接，所以稍微配置了一下让 squid 也支持 git 协议的链接。
url: /articles/squid-for-git-proxy.html
index_image:
  - https://www.digglife.net/wp-content/uploads/2014/12/squid.png
views:
  - 857
duoshuo_thread_id:
  - 1154125469839262202
wp-syntax-cache-content:
  - |
    a:5:{i:1;s:2439:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;">acl SSL_ports port <span style="color: #000000;">443</span>
    acl Safe_ports port <span style="color: #000000;">80</span>		<span style="color: #666666; font-style: italic;"># http</span>
    acl Safe_ports port <span style="color: #000000;">21</span>		<span style="color: #666666; font-style: italic;"># ftp</span>
    acl Safe_ports port <span style="color: #000000;">443</span>		<span style="color: #666666; font-style: italic;"># https</span>
    acl Safe_ports port <span style="color: #000000;">70</span>		<span style="color: #666666; font-style: italic;"># gopher</span>
    acl Safe_ports port <span style="color: #000000;">210</span>		<span style="color: #666666; font-style: italic;"># wais</span>
    acl Safe_ports port <span style="color: #000000;">1025</span>-<span style="color: #000000;">65535</span>	<span style="color: #666666; font-style: italic;"># unregistered ports</span>
    acl Safe_ports port <span style="color: #000000;">280</span>		<span style="color: #666666; font-style: italic;"># http-mgmt</span>
    acl Safe_ports port <span style="color: #000000;">488</span>		<span style="color: #666666; font-style: italic;"># gss-http</span>
    acl Safe_ports port <span style="color: #000000;">591</span>		<span style="color: #666666; font-style: italic;"># filemaker</span>
    acl Safe_ports port <span style="color: #000000;">777</span>		<span style="color: #666666; font-style: italic;"># multiling http</span>
    &nbsp;
    <span style="color: #666666; font-style: italic;">#add git protocol support</span>
    acl SSL_ports port <span style="color: #000000;">9418</span>
    acl Safe_ports port <span style="color: #000000;">9418</span>        <span style="color: #666666; font-style: italic;"># git port</span>
    acl CONNECT method CONNECT</pre></td></tr></table><p class="theCode" style="display:none;">acl SSL_ports port 443
    acl Safe_ports port 80		# http
    acl Safe_ports port 21		# ftp
    acl Safe_ports port 443		# https
    acl Safe_ports port 70		# gopher
    acl Safe_ports port 210		# wais
    acl Safe_ports port 1025-65535	# unregistered ports
    acl Safe_ports port 280		# http-mgmt
    acl Safe_ports port 488		# gss-http
    acl Safe_ports port 591		# filemaker
    acl Safe_ports port 777		# multiling http
    
    #add git protocol support
    acl SSL_ports port 9418
    acl Safe_ports port 9418        # git port
    acl CONNECT method CONNECT</p></div>
    ";i:2;s:381:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;">connect_timeout <span style="color: #000000;">5</span> minutes
    client_lifetime <span style="color: #000000;">5</span> minutes</pre></td></tr></table><p class="theCode" style="display:none;">connect_timeout 5 minutes
    client_lifetime 5 minutes</p></div>
    ";i:3;s:2282:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #666666; font-style: italic;">#!/bin/sh</span>
    <span style="color: #666666; font-style: italic;"># Use socat to proxy git through an HTTP CONNECT firewall.</span>
    <span style="color: #666666; font-style: italic;"># Useful if you are trying to clone git:// from inside a company.</span>
    <span style="color: #666666; font-style: italic;"># Requires that the proxy allows CONNECT to port 9418.</span>
    <span style="color: #666666; font-style: italic;">#</span>
    <span style="color: #666666; font-style: italic;"># Save this file as gitproxy somewhere in your path (e.g., ~/bin) and then run</span>
    <span style="color: #666666; font-style: italic;"># chmod +x gitproxy</span>
    <span style="color: #666666; font-style: italic;"># git config --global core.gitproxy gitproxy</span>
    <span style="color: #666666; font-style: italic;">#</span>
    <span style="color: #666666; font-style: italic;"># More details at http://tinyurl.com/8xvpny</span>
    <span style="color: #666666; font-style: italic;"># Configuration. Common proxy ports are 3128, 8123, 8000.</span>
    <span style="color: #007800;">_proxy</span>=proxy.yourcompany.com
    <span style="color: #007800;">_proxyport</span>=<span style="color: #000000;">3128</span>
    <span style="color: #7a0874; font-weight: bold;">exec</span> socat STDIO PROXY:<span style="color: #007800;">$_proxy</span>:<span style="color: #007800;">$1</span>:<span style="color: #007800;">$2</span>,<span style="color: #007800;">proxyport</span>=<span style="color: #007800;">$_proxyport</span></pre></td></tr></table><p class="theCode" style="display:none;">#!/bin/sh
    # Use socat to proxy git through an HTTP CONNECT firewall.
    # Useful if you are trying to clone git:// from inside a company.
    # Requires that the proxy allows CONNECT to port 9418.
    #
    # Save this file as gitproxy somewhere in your path (e.g., ~/bin) and then run
    # chmod +x gitproxy
    # git config --global core.gitproxy gitproxy
    #
    # More details at http://tinyurl.com/8xvpny
    # Configuration. Common proxy ports are 3128, 8123, 8000.
    _proxy=proxy.yourcompany.com
    _proxyport=3128
    exec socat STDIO PROXY:$_proxy:$1:$2,proxyport=$_proxyport</p></div>
    ";i:4;s:587:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #c20cb9; font-weight: bold;">git config</span> <span style="color: #660033;">--global</span> core.gitproxy <span style="color: #000000; font-weight: bold;">/</span>path<span style="color: #000000; font-weight: bold;">/</span>to<span style="color: #000000; font-weight: bold;">/</span>你的脚本名字</pre></td></tr></table><p class="theCode" style="display:none;">git config --global core.gitproxy /path/to/你的脚本名字</p></div>
    ";i:5;s:837:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #c20cb9; font-weight: bold;">git config</span> <span style="color: #660033;">--global</span> http.proxy http:<span style="color: #000000; font-weight: bold;">//</span>proxy.yourcompany.com:<span style="color: #000000;">3128</span>
    <span style="color: #c20cb9; font-weight: bold;">git config</span> <span style="color: #660033;">--global</span> https.proxy http:<span style="color: #000000; font-weight: bold;">//</span>proxy.yourcompany.com:<span style="color: #000000;">3128</span></pre></td></tr></table><p class="theCode" style="display:none;">git config --global http.proxy http://proxy.yourcompany.com:3128
    git config --global https.proxy http://proxy.yourcompany.com:3128</p></div>
    ";}
categories:
  - Ubuntu技巧
tags:
  - git
  - proxy
  - squid

---
内网机器需要 clone 一些 Github上的 Repo ，公司申请 Permissive IP 的流程非常麻烦，而且只是偶尔用用也没有太大必要，所以直接使用 Squid 代理解决了。本来 squid 默认支持 http 等常见协议，给 git 客户端配置一下 `http.proxy` 和 `https.proxy` 也足够了，但是这样每次 clone 的时候就只能使用 https 形式的链接，所以稍微配置了一下让 squid 也支持 git 协议的链接。

<!--more-->

<img src="http://digglife.qiniudn.com/wp-content/uploads/2016/05/squid-git.jpg" alt="配置Squid代理Git协议" width="500" height="118" />

### 1. Squid 添加 Git 端口

git 协议使用的是 9418 端口，所以需要在 squid.conf 里添加这个端口的支持。

<pre lang="bash">acl SSL_ports port 443
acl Safe_ports port 80		# http
acl Safe_ports port 21		# ftp
acl Safe_ports port 443		# https
acl Safe_ports port 70		# gopher
acl Safe_ports port 210		# wais
acl Safe_ports port 1025-65535	# unregistered ports
acl Safe_ports port 280		# http-mgmt
acl Safe_ports port 488		# gss-http
acl Safe_ports port 591		# filemaker
acl Safe_ports port 777		# multiling http

#add git protocol support
acl SSL_ports port 9418
acl Safe_ports port 9418        # git port
acl CONNECT method CONNECT
</pre>

编辑完成之后使用 `squid -k reconfigure` 重新载入配置文件。

注意，因为有些 Git Repo 数据量庞大，如果网速不是很快的话，建议将超时的时间设长一点，默认是1分钟。

<pre lang="bash">connect_timeout 5 minutes
client_lifetime 5 minutes
</pre>

### 2. Git 代理脚本设置

现在 squid 已经支持连接 9418 端口了，那么本地需要做的就是让 git 协议的流量全部通过 squid 代理转发，这里我们用到神器 socat。Shell 脚本如下，详情见<a href="http://www.emilsit.net/blog/archives/how-to-use-the-git-protocol-through-a-http-connect-proxy/" title="How to Use the Git Protocol Through a HTTP CONNECT Proxy" target="_blank">这篇博客</a>。

<pre lang="bash">#!/bin/sh
# Use socat to proxy git through an HTTP CONNECT firewall.
# Useful if you are trying to clone git:// from inside a company.
# Requires that the proxy allows CONNECT to port 9418.
#
# Save this file as gitproxy somewhere in your path (e.g., ~/bin) and then run
# chmod +x gitproxy
# git config --global core.gitproxy gitproxy
#
# More details at http://tinyurl.com/8xvpny
# Configuration. Common proxy ports are 3128, 8123, 8000.
_proxy=proxy.yourcompany.com
_proxyport=3128
exec socat STDIO PROXY:$_proxy:$1:$2,proxyport=$_proxyport
</pre>

更改里面代理的地址和端口，保存到一个合适的位置，比如`~/bin`，并加上执行权限。

### 3. 配置git客户端代理

上一步中的脚本，最好放在$PATH中的路径下，这样配置的时候就不用使用绝对路径了。执行一下命令配置git代理。

<pre lang="bash">git config --global core.gitproxy /path/to/你的脚本名字
</pre>

现在就可以试试 clone git协议的repo了。

### 4. HTTP/HTTPS 代理

顺便提一下 git 的 HTTP/HTTPS 代理设置。

<pre lang="bash">git config --global http.proxy http://proxy.yourcompany.com:3128
git config --global https.proxy http://proxy.yourcompany.com:3128
</pre>