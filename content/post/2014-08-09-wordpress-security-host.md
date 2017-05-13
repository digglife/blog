---
title: 加固 WordPress 安全性的几个简单方法（服务器篇）
author: 摩摩诘
type: post
date: 2014-08-08T18:04:45+00:00
excerpt: Wordpress的安全性其实不错，但是如果服务器上不做一些基本的安全措施，Wordpress再安全也是白搭。现在的VPS相比几年前便宜很多，很多人都买了自己的独立主机，如果不注意安全，网站被挂马，主机变毒瘤都是分分钟的事。但其实只要注意一些最基本的安全因素，就能避免大部分的低级攻击。前些天整理自己的服务器的时候发现一些问题，这里总结一下，以后再搬服务器也好参考。
url: /articles/wordpress-security-host.html
index_image:
  - https://www.digglife.net/wp-content/uploads/2014/08/secure-wordpress.jpg
views:
  - 386
duoshuo_thread_id:
  - 1154125469839262186
wp-syntax-cache-content:
  - |
    a:7:{i:1;s:600:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="line_numbers"><pre>1
    2
    3
    </pre></td><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #666666; font-style: italic;">#把默认的22更改成自定义的数字</span>
    <span style="color: #666666; font-style: italic;"># What ports, IPs and protocols we listen for</span>
    Port <span style="color: #000000;">8964</span></pre></td></tr></table><p class="theCode" style="display:none;">#把默认的22更改成自定义的数字
    # What ports, IPs and protocols we listen for
    Port 8964</p></div>
    ";i:2;s:497:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="line_numbers"><pre>1
    2
    3
    </pre></td><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #666666; font-style: italic;">#/etc/ssh/sshd_config</span>
    <span style="color: #666666; font-style: italic;">#把默认的yes改成no</span>
    PermitRootLogin no</pre></td></tr></table><p class="theCode" style="display:none;">#/etc/ssh/sshd_config
    #把默认的yes改成no
    PermitRootLogin no</p></div>
    ";i:3;s:6444:"
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
    </pre></td><td class="code"><pre class="bash" style="font-family:monospace;">Jul <span style="color: #000000;">27</span> 06:<span style="color: #000000;">29</span>:<span style="color: #000000;">17</span> localhost sshd<span style="color: #7a0874; font-weight: bold;">&#91;</span><span style="color: #000000;">10509</span><span style="color: #7a0874; font-weight: bold;">&#93;</span>: input_userauth_request: invalid user old <span style="color: #7a0874; font-weight: bold;">&#91;</span>preauth<span style="color: #7a0874; font-weight: bold;">&#93;</span>
    Jul <span style="color: #000000;">27</span> 06:<span style="color: #000000;">31</span>:04 localhost sshd<span style="color: #7a0874; font-weight: bold;">&#91;</span><span style="color: #000000;">10511</span><span style="color: #7a0874; font-weight: bold;">&#93;</span>: input_userauth_request: invalid user oracle <span style="color: #7a0874; font-weight: bold;">&#91;</span>preauth<span style="color: #7a0874; font-weight: bold;">&#93;</span>
    Jul <span style="color: #000000;">27</span> 06:<span style="color: #000000;">37</span>:<span style="color: #000000;">30</span> localhost sshd<span style="color: #7a0874; font-weight: bold;">&#91;</span><span style="color: #000000;">10516</span><span style="color: #7a0874; font-weight: bold;">&#93;</span>: input_userauth_request: invalid user abc <span style="color: #7a0874; font-weight: bold;">&#91;</span>preauth<span style="color: #7a0874; font-weight: bold;">&#93;</span>
    Jul <span style="color: #000000;">27</span> 06:<span style="color: #000000;">38</span>:<span style="color: #000000;">25</span> localhost sshd<span style="color: #7a0874; font-weight: bold;">&#91;</span><span style="color: #000000;">10518</span><span style="color: #7a0874; font-weight: bold;">&#93;</span>: input_userauth_request: invalid user oracle <span style="color: #7a0874; font-weight: bold;">&#91;</span>preauth<span style="color: #7a0874; font-weight: bold;">&#93;</span>
    Jul <span style="color: #000000;">27</span> 06:<span style="color: #000000;">45</span>:<span style="color: #000000;">40</span> localhost sshd<span style="color: #7a0874; font-weight: bold;">&#91;</span><span style="color: #000000;">10534</span><span style="color: #7a0874; font-weight: bold;">&#93;</span>: input_userauth_request: invalid user postgres <span style="color: #7a0874; font-weight: bold;">&#91;</span>preauth<span style="color: #7a0874; font-weight: bold;">&#93;</span>
    Jul <span style="color: #000000;">27</span> 06:<span style="color: #000000;">53</span>:<span style="color: #000000;">46</span> localhost sshd<span style="color: #7a0874; font-weight: bold;">&#91;</span><span style="color: #000000;">10557</span><span style="color: #7a0874; font-weight: bold;">&#93;</span>: input_userauth_request: invalid user rose <span style="color: #7a0874; font-weight: bold;">&#91;</span>preauth<span style="color: #7a0874; font-weight: bold;">&#93;</span>
    Jul <span style="color: #000000;">27</span> 07:07:<span style="color: #000000;">42</span> localhost sshd<span style="color: #7a0874; font-weight: bold;">&#91;</span><span style="color: #000000;">10570</span><span style="color: #7a0874; font-weight: bold;">&#93;</span>: input_userauth_request: invalid user testing <span style="color: #7a0874; font-weight: bold;">&#91;</span>preauth<span style="color: #7a0874; font-weight: bold;">&#93;</span>
    Jul <span style="color: #000000;">27</span> 07:09:<span style="color: #000000;">57</span> localhost sshd<span style="color: #7a0874; font-weight: bold;">&#91;</span><span style="color: #000000;">10581</span><span style="color: #7a0874; font-weight: bold;">&#93;</span>: input_userauth_request: invalid user abcd <span style="color: #7a0874; font-weight: bold;">&#91;</span>preauth<span style="color: #7a0874; font-weight: bold;">&#93;</span>
    Jul <span style="color: #000000;">27</span> 07:<span style="color: #000000;">15</span>:04 localhost sshd<span style="color: #7a0874; font-weight: bold;">&#91;</span><span style="color: #000000;">10586</span><span style="color: #7a0874; font-weight: bold;">&#93;</span>: input_userauth_request: invalid user <span style="color: #7a0874; font-weight: bold;">test</span> <span style="color: #7a0874; font-weight: bold;">&#91;</span>preauth<span style="color: #7a0874; font-weight: bold;">&#93;</span>
    Jul <span style="color: #000000;">27</span> 07:<span style="color: #000000;">18</span>:01 localhost sshd<span style="color: #7a0874; font-weight: bold;">&#91;</span><span style="color: #000000;">10591</span><span style="color: #7a0874; font-weight: bold;">&#93;</span>: input_userauth_request: invalid user lion <span style="color: #7a0874; font-weight: bold;">&#91;</span>preauth<span style="color: #7a0874; font-weight: bold;">&#93;</span>
    Jul <span style="color: #000000;">27</span> 07:<span style="color: #000000;">22</span>:<span style="color: #000000;">24</span> localhost sshd<span style="color: #7a0874; font-weight: bold;">&#91;</span><span style="color: #000000;">10593</span><span style="color: #7a0874; font-weight: bold;">&#93;</span>: input_userauth_request: invalid user testuser <span style="color: #7a0874; font-weight: bold;">&#91;</span>preauth<span style="color: #7a0874; font-weight: bold;">&#93;</span></pre></td></tr></table><p class="theCode" style="display:none;">Jul 27 06:29:17 localhost sshd[10509]: input_userauth_request: invalid user old [preauth]
    Jul 27 06:31:04 localhost sshd[10511]: input_userauth_request: invalid user oracle [preauth]
    Jul 27 06:37:30 localhost sshd[10516]: input_userauth_request: invalid user abc [preauth]
    Jul 27 06:38:25 localhost sshd[10518]: input_userauth_request: invalid user oracle [preauth]
    Jul 27 06:45:40 localhost sshd[10534]: input_userauth_request: invalid user postgres [preauth]
    Jul 27 06:53:46 localhost sshd[10557]: input_userauth_request: invalid user rose [preauth]
    Jul 27 07:07:42 localhost sshd[10570]: input_userauth_request: invalid user testing [preauth]
    Jul 27 07:09:57 localhost sshd[10581]: input_userauth_request: invalid user abcd [preauth]
    Jul 27 07:15:04 localhost sshd[10586]: input_userauth_request: invalid user test [preauth]
    Jul 27 07:18:01 localhost sshd[10591]: input_userauth_request: invalid user lion [preauth]
    Jul 27 07:22:24 localhost sshd[10593]: input_userauth_request: invalid user testuser [preauth]</p></div>
    ";i:4;s:2734:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="line_numbers"><pre>1
    2
    3
    4
    5
    6
    7
    </pre></td><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #666666; font-style: italic;">#系统帐号示例</span>
    root:x:<span style="color: #000000;">0</span>:<span style="color: #000000;">0</span>:root:<span style="color: #000000; font-weight: bold;">/</span>root:<span style="color: #000000; font-weight: bold;">/</span>bin<span style="color: #000000; font-weight: bold;">/</span><span style="color: #c20cb9; font-weight: bold;">bash</span>
    daemon:x:<span style="color: #000000;">1</span>:<span style="color: #000000;">1</span>:daemon:<span style="color: #000000; font-weight: bold;">/</span>usr<span style="color: #000000; font-weight: bold;">/</span>sbin:<span style="color: #000000; font-weight: bold;">/</span>usr<span style="color: #000000; font-weight: bold;">/</span>sbin<span style="color: #000000; font-weight: bold;">/</span>nologin
    bin:x:<span style="color: #000000;">2</span>:<span style="color: #000000;">2</span>:bin:<span style="color: #000000; font-weight: bold;">/</span>bin:<span style="color: #000000; font-weight: bold;">/</span>usr<span style="color: #000000; font-weight: bold;">/</span>sbin<span style="color: #000000; font-weight: bold;">/</span>nologin
    sys:x:<span style="color: #000000;">3</span>:<span style="color: #000000;">3</span>:sys:<span style="color: #000000; font-weight: bold;">/</span>dev:<span style="color: #000000; font-weight: bold;">/</span>usr<span style="color: #000000; font-weight: bold;">/</span>sbin<span style="color: #000000; font-weight: bold;">/</span>nologin
    sync:x:<span style="color: #000000;">4</span>:<span style="color: #000000;">65534</span>:sync:<span style="color: #000000; font-weight: bold;">/</span>bin:<span style="color: #000000; font-weight: bold;">/</span>bin<span style="color: #000000; font-weight: bold;">/</span><span style="color: #c20cb9; font-weight: bold;">sync</span>
    games:x:<span style="color: #000000;">5</span>:<span style="color: #000000;">60</span>:games:<span style="color: #000000; font-weight: bold;">/</span>usr<span style="color: #000000; font-weight: bold;">/</span>games:<span style="color: #000000; font-weight: bold;">/</span>usr<span style="color: #000000; font-weight: bold;">/</span>sbin<span style="color: #000000; font-weight: bold;">/</span>nologin</pre></td></tr></table><p class="theCode" style="display:none;">#系统帐号示例
    root:x:0:0:root:/root:/bin/bash
    daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
    bin:x:2:2:bin:/bin:/usr/sbin/nologin
    sys:x:3:3:sys:/dev:/usr/sbin/nologin
    sync:x:4:65534:sync:/bin:/bin/sync
    games:x:5:60:games:/usr/games:/usr/sbin/nologin</p></div>
    ";i:5;s:948:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="line_numbers"><pre>1
    2
    3
    4
    5
    6
    7
    </pre></td><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #666666; font-style: italic;">#/etc/ssh/sshd_config</span>
    <span style="color: #666666; font-style: italic;">#公钥认证方式一般默认是开启的，无需更改</span>
    RSAAuthentication <span style="color: #c20cb9; font-weight: bold;">yes</span>
    PubkeyAuthentication <span style="color: #c20cb9; font-weight: bold;">yes</span>
    &nbsp;
    <span style="color: #666666; font-style: italic;">#密码认证方式默认是yes，改成no</span>
    PasswordAuthentication no</pre></td></tr></table><p class="theCode" style="display:none;">#/etc/ssh/sshd_config
    #公钥认证方式一般默认是开启的，无需更改
    RSAAuthentication yes
    PubkeyAuthentication yes
    
    #密码认证方式默认是yes，改成no
    PasswordAuthentication no</p></div>
    ";i:6;s:4655:"
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
    </pre></td><td class="code"><pre class="bash" style="font-family:monospace;"><span style="display:block;background-color: #ffc;"><span style="color: #666666;">zhu@digglife:~$ </span><span style="color: #c20cb9; font-weight: bold;">sudo</span> <span style="color: #c20cb9; font-weight: bold;">netstat</span> <span style="color: #660033;">-tlunp</span></span>Active Internet connections <span style="color: #7a0874; font-weight: bold;">&#40;</span>only servers<span style="color: #7a0874; font-weight: bold;">&#41;</span>
    Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID<span style="color: #000000; font-weight: bold;">/</span>Program name
    tcp        <span style="color: #000000;">0</span>      <span style="color: #000000;">0</span> 127.0.0.1:<span style="color: #000000;">8001</span>          0.0.0.0:<span style="color: #000000; font-weight: bold;">*</span>               LISTEN      <span style="color: #000000;">7044</span><span style="color: #000000; font-weight: bold;">/</span>uwsgi      
    tcp        <span style="color: #000000;">0</span>      <span style="color: #000000;">0</span> 127.0.0.1:<span style="color: #000000;">3306</span>          0.0.0.0:<span style="color: #000000; font-weight: bold;">*</span>               LISTEN      <span style="color: #000000;">23725</span><span style="color: #000000; font-weight: bold;">/</span>mysqld    
    tcp        <span style="color: #000000;">0</span>      <span style="color: #000000;">0</span> 127.0.0.1:<span style="color: #000000;">11211</span>         0.0.0.0:<span style="color: #000000; font-weight: bold;">*</span>               LISTEN      <span style="color: #000000;">27557</span><span style="color: #000000; font-weight: bold;">/</span>memcached 
    tcp        <span style="color: #000000;">0</span>      <span style="color: #000000;">0</span> 0.0.0.0:<span style="color: #000000;">80</span>              0.0.0.0:<span style="color: #000000; font-weight: bold;">*</span>               LISTEN      <span style="color: #000000;">8281</span><span style="color: #000000; font-weight: bold;">/</span>nginx: worker 
    tcp        <span style="color: #000000;">0</span>      <span style="color: #000000;">0</span> 0.0.0.0:xxxx            0.0.0.0:<span style="color: #000000; font-weight: bold;">*</span>               LISTEN      <span style="color: #000000;">16421</span><span style="color: #000000; font-weight: bold;">/</span>sshd      
    tcp        <span style="color: #000000;">0</span>      <span style="color: #000000;">0</span> 0.0.0.0:xxxx            0.0.0.0:<span style="color: #000000; font-weight: bold;">*</span>               LISTEN      <span style="color: #000000;">8281</span><span style="color: #000000; font-weight: bold;">/</span>nginx: worker 
    tcp6       <span style="color: #000000;">0</span>      <span style="color: #000000;">0</span> :::xxxx                 :::<span style="color: #000000; font-weight: bold;">*</span>                    LISTEN      <span style="color: #000000;">16421</span><span style="color: #000000; font-weight: bold;">/</span>sshd      
    udp        <span style="color: #000000;">0</span>      <span style="color: #000000;">0</span> 127.0.0.1:<span style="color: #000000;">11211</span>         0.0.0.0:<span style="color: #000000; font-weight: bold;">*</span>                           <span style="color: #000000;">27557</span><span style="color: #000000; font-weight: bold;">/</span>memcached 
    <span style="color: #666666;">zhu@digglife:~$</span></pre></td></tr></table><p class="theCode" style="display:none;">zhu@digglife:~$ sudo netstat -tlunp
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name
    tcp        0      0 127.0.0.1:8001          0.0.0.0:*               LISTEN      7044/uwsgi      
    tcp        0      0 127.0.0.1:3306          0.0.0.0:*               LISTEN      23725/mysqld    
    tcp        0      0 127.0.0.1:11211         0.0.0.0:*               LISTEN      27557/memcached 
    tcp        0      0 0.0.0.0:80              0.0.0.0:*               LISTEN      8281/nginx: worker 
    tcp        0      0 0.0.0.0:xxxx            0.0.0.0:*               LISTEN      16421/sshd      
    tcp        0      0 0.0.0.0:xxxx            0.0.0.0:*               LISTEN      8281/nginx: worker 
    tcp6       0      0 :::xxxx                 :::*                    LISTEN      16421/sshd      
    udp        0      0 127.0.0.1:11211         0.0.0.0:*                           27557/memcached 
    zhu@digglife:~$</p></div>
    ";i:7;s:922:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="line_numbers"><pre>1
    2
    3
    4
    </pre></td><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #666666; font-style: italic;"># Specify which IP address to listen on. The default is to listen on all IP addresses</span>
    <span style="color: #666666; font-style: italic;"># This parameter is one of the only security measures that memcached has, so make sure</span>
    <span style="color: #666666; font-style: italic;"># it's listening on a firewalled interface.</span>
    <span style="color: #660033;">-l</span> 127.0.0.1</pre></td></tr></table><p class="theCode" style="display:none;"># Specify which IP address to listen on. The default is to listen on all IP addresses
    # This parameter is one of the only security measures that memcached has, so make sure
    # it's listening on a firewalled interface.
    -l 127.0.0.1</p></div>
    ";}
categories:
  - Ubuntu技巧
tags:
  - Linux
  - wordpress
  - 安全

---
WordPress的安全性其实不错，但是如果服务器上不做一些基本的安全措施，Wordpress再安全也是白搭。现在的VPS相比几年前便宜很多，很多人都买了自己的独立主机，如果不注意安全，面对满世界全天候的自动攻击脚本，网站被挂马，主机变毒瘤都是分分钟的事。

等中招之后再排查就异常困难了，因为可能有问题的点太多，逐一排查也不见得不会有漏网之鱼。但是其实只要注意一些最基本的安全因素，就能避免大部分低级攻击，免去不必要的麻烦。

前些天整理自己的服务器的时候发现一些问题，这里总结一下，以后再搬服务器也好参考。
  
<!--more-->

### 1. 更改SSH默认端口

网上很多自动攻击脚本通过循环试错来破解账户密码的，尝试的端口都有限，所以如果把SSH端口改成4位数的，比如8964就不错，能够规避多数暴力破解攻击。注：UNIX系OS的端口限制是0~2^16-1（也就是0~65535），<a href="http://en.wikipedia.org/wiki/List_of_TCP_and_UDP_port_numbers" title="常用软件的TCP/UDP端口列表" target="_blank">一些端口已经被知名软件占用了</a>，但是只要自己的服务器上不冲突就行。

编辑 `/etc/ssh/sshd_config` 文件：

<pre lang='bash' line='1'>#把默认的22更改成自定义的数字
# What ports, IPs and protocols we listen for
Port 8964
</pre>

### 2. 禁用root SSH登录

目的同上。Root密码的破解是攻击脚本的首要目标，所以还是新建一个私人账户，赋予sudo权限即可。嫌每次sudo输入密码麻烦，加上NOPASSWD指令，影响不大。

<pre lang='bash' line='1'>#/etc/ssh/sshd_config
#把默认的yes改成no
PermitRootLogin no
</pre>

### 3. 取一个独特的用户名

攻击脚本会尝试很多用户名，一部分是常用服务的默认用户名，还有一些是人们喜欢使用的用户名。所以像admin，tester，jack什么之类的用户名就不要了。下面是我从log中取出来的一小部分，常用服务帐号，常用人名什么之类的都有，只有想不到，没有做不到，实在叹为观止。

<pre lang='bash' line='1'>Jul 27 06:29:17 localhost sshd[10509]: input_userauth_request: invalid user old [preauth]
Jul 27 06:31:04 localhost sshd[10511]: input_userauth_request: invalid user oracle [preauth]
Jul 27 06:37:30 localhost sshd[10516]: input_userauth_request: invalid user abc [preauth]
Jul 27 06:38:25 localhost sshd[10518]: input_userauth_request: invalid user oracle [preauth]
Jul 27 06:45:40 localhost sshd[10534]: input_userauth_request: invalid user postgres [preauth]
Jul 27 06:53:46 localhost sshd[10557]: input_userauth_request: invalid user rose [preauth]
Jul 27 07:07:42 localhost sshd[10570]: input_userauth_request: invalid user testing [preauth]
Jul 27 07:09:57 localhost sshd[10581]: input_userauth_request: invalid user abcd [preauth]
Jul 27 07:15:04 localhost sshd[10586]: input_userauth_request: invalid user test [preauth]
Jul 27 07:18:01 localhost sshd[10591]: input_userauth_request: invalid user lion [preauth]
Jul 27 07:22:24 localhost sshd[10593]: input_userauth_request: invalid user testuser [preauth]
</pre>

### 4. 禁用不必要的Shell

检查`/etc/passwd`。一般来说，预置帐号除了root之外都是没有shell的，如果你发现类似man,game,sys这样的系统帐号的最后一列都是 `/bin/sh` 之类的shell，那就得注意一下了。各个系统的nologin位置不一样，`locate`一下。Ubuntu默认是`/usr/sbin/nologin`或者`/bin/false`，这两者有一点<a href="http://www.cyberciti.biz/faq/linux-binfalse-vs-sbinnologin-deny-login/" title="/sbin/nologin和/bin/false的区别" target="_blank">细微的区别</a>。

<pre lang='bash' line='1'>#系统帐号示例
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
games:x:5:60:games:/usr/games:/usr/sbin/nologin
</pre>

### 4. 使用公钥认证

如果使用上面的这些还不够，还可以彻底禁用密码登录的方式，采用公钥认证登录。当然，使用这种方式之后不方便随时随地管理，但是一个自用的web服务器，随时登录的需求几乎没有，在自己经常用的几台电脑上有密钥就好了。

<pre lang='bash' line='1'>#/etc/ssh/sshd_config
#公钥认证方式一般默认是开启的，无需更改
RSAAuthentication yes
PubkeyAuthentication yes

#密码认证方式默认是yes，改成no
PasswordAuthentication no
</pre>

### 5. 停用不必要的服务

比如 vsftpd ，如果之前使用过现在不需要了，记得停用，然后彻底禁用掉。少一个服务少一个威胁。另外，像 FTP 这种服务，能不用就不用了，需要传文件的时候SCP足矣。可以用 `netstat` 命令查一下有监听端口的服务，然后排除不必要的。

<pre lang='bash' line='1' highlight='1'>zhu@digglife:~$ sudo netstat -tlunp
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name
tcp        0      0 127.0.0.1:8001          0.0.0.0:*               LISTEN      7044/uwsgi      
tcp        0      0 127.0.0.1:3306          0.0.0.0:*               LISTEN      23725/mysqld    
tcp        0      0 127.0.0.1:11211         0.0.0.0:*               LISTEN      27557/memcached 
tcp        0      0 0.0.0.0:80              0.0.0.0:*               LISTEN      8281/nginx: worker 
tcp        0      0 0.0.0.0:xxxx            0.0.0.0:*               LISTEN      16421/sshd      
tcp        0      0 0.0.0.0:xxxx            0.0.0.0:*               LISTEN      8281/nginx: worker 
tcp6       0      0 :::xxxx                 :::*                    LISTEN      16421/sshd      
udp        0      0 127.0.0.1:11211         0.0.0.0:*                           27557/memcached 
zhu@digglife:~$ 
</pre>

### 6. 辅助服务只监听本地回环

某些服务只提供给本地的其他软件，比如 WordPress 必要的 MySQL，缓存插件用的 memcached 等等，只要是提供本地服务的，都设置为监听127.0.0.1，能规避直接的远程攻击。以 memcached 为例，配置文件为 `/etc/memcached.conf` ，默认监听所有IP。

<pre lang='bash' line='1'># Specify which IP address to listen on. The default is to listen on all IP addresses
# This parameter is one of the only security measures that memcached has, so make sure
# it's listening on a firewalled interface.
-l 127.0.0.1
</pre>

设置好重启服务之后惯例 `netstat` 检查一下。

以上这些只是最基本的服务器防护，实施起来十分简单，而且不会带来使用上的不方便。复杂的安全方式当然还有，比如使用iptables设定防火墙过滤，更改UMASK，开启Audit等等等等，但是比较复杂，多有妨碍自己方便的情况，何况一般也用不着。

对于服务器本身这一方面，如果想进一步做安全配置，可以分析一下一天的 security 相关log，RH系在 `/var/log/secure` ，Debian系在 `/var/log/auth.log` ，基本上能够了解攻击的类型，然后采取有针对性的措施。