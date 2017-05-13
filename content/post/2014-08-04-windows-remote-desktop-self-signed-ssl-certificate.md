---
title: 给 Windows 远程桌面服务生成自认证SSL证书
author: 摩摩诘
type: post
date: 2014-08-04T15:00:14+00:00
excerpt: 使用微软官方提供的 Makecert 工具生成自认证SSL证书，以达到加密远程桌面服务连接的目的。Windows 从 2000 开始支持 SSL 加密远程桌面服务，只要在远程桌面服务设置里指定一个证书，RDP设置的加密方式那里就会出现SSL选项（从Windows Server 2008开始默认内置用于远程桌面服务的自认证证书）。
url: /articles/windows-remote-desktop-self-signed-ssl-certificate.html
views:
  - 824
duoshuo_thread_id:
  - 1154125469839262185
index_image:
  - https://www.digglife.net/wp-content/uploads/2014/08/windows8-remote-desktop.jpg
wp-syntax-cache-content:
  - |
    a:1:{i:1;s:1361:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;">makecert <span style="color: #660033;">-r</span> <span style="color: #660033;">-pe</span> <span style="color: #660033;">-n</span> <span style="color: #ff0000;">&quot;CN=digglife.net&quot;</span> <span style="color: #660033;">-e</span> 01<span style="color: #000000; font-weight: bold;">/</span>01<span style="color: #000000; font-weight: bold;">/</span><span style="color: #000000;">2040</span> <span style="color: #660033;">-eku</span> 1.3.6.1.5.5.7.3.1 <span style="color: #660033;">-ss</span> my <span style="color: #660033;">-sr</span> localMachine <span style="color: #660033;">-sky</span> exchange <span style="color: #660033;">-sp</span> <span style="color: #ff0000;">&quot;Microsoft RSA SChannel Cryptographic Provider&quot;</span> <span style="color: #660033;">-sy</span> <span style="color: #000000;">12</span> <span style="color: #660033;">-a</span> SHA1 <span style="color: #660033;">-len</span> <span style="color: #000000;">2048</span></pre></td></tr></table><p class="theCode" style="display:none;">makecert -r -pe -n &quot;CN=digglife.net&quot; -e 01/01/2040 -eku 1.3.6.1.5.5.7.3.1 -ss my -sr localMachine -sky exchange -sp &quot;Microsoft RSA SChannel Cryptographic Provider&quot; -sy 12 -a SHA1 -len 2048</p></div>
    ";}
categories:
  - Windows技巧
tags:
  - ssl
  - windows
  - 证书
  - 远程桌面

---
Windows 从 2000 开始支持 SSL 加密 远程桌面服务，只要在远程桌面服务设置里指定一个证书，RDP设置的加密方式那里就会出现SSL选项（从Windows Server 2008开始默认内置用于远程桌面服务的自认证证书）。问题是 Windows 证书管理方式和 Linux 下有很大的不同，所有证书都由 OS 集中管理在一个类似数据库的容器里，需要用到证书的服务或者应用通过 WMI 从这个容器里获取。因为标准 Window 证书都有指定的 OID ，匹配的就会出现在服务或者应用的证书目录下。

微软官方文档里提到过如何生成标准的 Windows 证书，但是都依赖于Domain，而我想要的是像 OpenSSL 那样可以通过命令行直接生成自认证证书的工具。微软为了开发者测试应用的方便，提供了一批小工具，其中就包括一个 makecert 的命令行工具，让开发者可以通过命令行创建用于测试的自认证证书。

[Makecert 的语法][1]也不算复杂，手册清楚明白，只是一些有微软特色的参数要注意。

范例一枚：

<pre lang='bash'>makecert -r -pe -n "CN=digglife.net" -e 01/01/2040 -eku 1.3.6.1.5.5.7.3.1 -ss my -sr localMachine -sky exchange -sp "Microsoft RSA SChannel Cryptographic Provider" -sy 12 -a SHA1 -len 2048
</pre>

通过这个命令生成证书后，我们可以在证书管理控制台的“个人”证书下找到。

<img src="http://digglife.qiniudn.com/wp-content/uploads/2014/06/rdp-ssl-certificate.png" alt="查看远程桌面服务SSL自认证证书" width="484" height="352" class="alignnone size-full wp-image-3830" />

记录一下一些和生成远程桌面服务SSL证书相关的参数，详细信息参考MSDN的文档。

`-r` ： 生成自认证证书。
  
`-pe` ： 私钥标记为可导出（私钥包含在证书中）。
  
`-n` ： 证书名称 （CN=,OU=,O= blahblah）。
  
`-e` ： 证书失效日期。
  
`-eku` ： OID名称。`1.3.6.1.5.5.7.3.1`就是“服务器身份验证”的OID
  
`-ss` ： 证书存储名称。my代表的是Personal。
  
`-sr` ： 证书存储位置。LocalMachine或者CurrentUser。
  
`-sky` ： 密钥类型。
  
`-sp` ： 加密API的名称。
  
`-sy` ：加密API的类型。
  
`-a` ： 加密算法。
  
`-len` ： 密钥长度。

本来 makecert.exe 是集成在[.Net Framework开发包][2]里的，但是为了这么个小工具下载一个硕大的SDK实在很扯，所以提了一个出来放在这里。

[Makecert.exe 下载][3]

 [1]: http://msdn.microsoft.com/zh-cn/library/bfsktky3(v=vs.110).aspx
 [2]: www.microsoft.com/en-us/download/details.aspx?id=8279 ".Net Framework 4 SDK"
 [3]: https://www.digglife.net/wp-content/uploads/files/makecert.zip "Windows SSL证书生成工具makecert.exe下载"