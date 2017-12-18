---
title: 配置Squid代理Git协议
author: 摩摩诘
type: post
date: 2014-12-19T06:02:07+00:00
excerpt: 本来 squid 默认支持 http 等常见协议，给 git 客户端配置一下 http.proxy 和 https.proxy 也足够了，但是这样每次 clone 的时候就只能使用 https 形式的链接，所以稍微配置了一下让 squid 也支持 git 协议的链接。
url: /articles/squid-for-git-proxy.html
index_image:
  - https://www.digglife.net/wp-content/uploads/2014/12/squid.png
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

    ```bash
    acl SSL_ports port 443
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
    ```

编辑完成之后使用 `squid -k reconfigure` 重新载入配置文件。

注意，因为有些 Git Repo 数据量庞大，如果网速不是很快的话，建议将超时的时间设长一点，默认是1分钟。

```
client_lifetime 5 minutes
```

### 2. Git 代理脚本设置

现在 squid 已经支持连接 9418 端口了，那么本地需要做的就是让 git 协议的流量全部通过 squid 代理转发，这里我们用到神器 socat。Shell 脚本如下，详情见<a href="http://www.emilsit.net/blog/archives/how-to-use-the-git-protocol-through-a-http-connect-proxy/" title="How to Use the Git Protocol Through a HTTP CONNECT Proxy" target="_blank">这篇博客</a>。

```bash
#!/bin/sh
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
```

更改里面代理的地址和端口，保存到一个合适的位置，比如`~/bin`，并加上执行权限。

### 3. 配置git客户端代理


```bash
git config --global core.gitproxy /path/to/你的脚本名字
```

现在就可以试试 clone git协议的repo了。

### 4. HTTP/HTTPS 代理

顺便提一下 git 的 HTTP/HTTPS 代理设置。

<pre lang="bash">git config --global http.proxy http://proxy.yourcompany.com:3128
git config --global https.proxy http://proxy.yourcompany.com:3128
</pre>