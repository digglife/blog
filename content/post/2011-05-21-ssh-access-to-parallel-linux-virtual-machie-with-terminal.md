---
title: 用Mac终端SSH连接到Parallel创建的Linux虚拟机
author: 摩摩诘
type: post
date: 2011-05-21T14:59:20+00:00
excerpt: 在Mac OS X的终端里SSH登陆到Fedora虚拟机，这样一来能够节省系统资源，二来不用在虚拟机和本机之间切换，省去很多麻烦，三来可以让自己习惯命令行的操作方式，一举多得。这里介绍了实现从本地终端SSH登陆到Linux虚拟机的方法。
url: /articles/ssh-access-to-parallel-linux-virtual-machie-with-terminal.html
views:
  - 12054
index_image:
  - https://www.digglife.net/wp-content/uploads/2011/05/ssh.png
bot_views:
  - 73
duoshuo_thread_id:
  - 1154125469839262149
wp-syntax-cache-content:
  - |
    a:8:{i:1;s:3594:"
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
    13
    14
    15
    16
    17
    18
    19
    20
    21
    22
    23
    24
    25
    </pre></td><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #7a0874; font-weight: bold;">&#91;</span>root<span style="color: #000000; font-weight: bold;">@</span>Mac <span style="color: #000000; font-weight: bold;">/</span><span style="color: #7a0874; font-weight: bold;">&#93;</span>$ <span style="color: #c20cb9; font-weight: bold;">vi</span> <span style="color: #000000; font-weight: bold;">/</span>etc<span style="color: #000000; font-weight: bold;">/</span>inittab
    &nbsp;
    <span style="color: #666666; font-style: italic;">#</span>
    <span style="color: #666666; font-style: italic;"># System initialization is started by /etc/init/rcS.conf</span>
    <span style="color: #666666; font-style: italic;">#</span>
    <span style="color: #666666; font-style: italic;"># Individual runlevels are started by /etc/init/rc.conf</span>
    <span style="color: #666666; font-style: italic;">#</span>
    <span style="color: #666666; font-style: italic;"># Ctrl-Alt-Delete is handled by /etc/init/control-alt-delete.conf</span>
    <span style="color: #666666; font-style: italic;">#</span>
    <span style="color: #666666; font-style: italic;"># Terminal gettys are handled by /etc/init/tty.conf and /etc/init/serial.conf,</span>
    <span style="color: #666666; font-style: italic;"># with configuration in /etc/sysconfig/init.</span>
    <span style="color: #666666; font-style: italic;">#</span>
    <span style="color: #666666; font-style: italic;"># For information on how to write upstart event handlers, or how</span>
    <span style="color: #666666; font-style: italic;"># upstart works, see init(5), init(8), and initctl(8).</span>
    <span style="color: #666666; font-style: italic;">#</span>
    <span style="color: #666666; font-style: italic;"># Default runlevel. The runlevels used are:</span>
    <span style="color: #666666; font-style: italic;">#   0 - halt (Do NOT set initdefault to this)</span>
    <span style="color: #666666; font-style: italic;">#   1 - Single user mode</span>
    <span style="color: #666666; font-style: italic;">#   2 - Multiuser, without NFS (The same as 3, if you do not have networking)</span>
    <span style="color: #666666; font-style: italic;">#   3 - Full multiuser mode</span>
    <span style="color: #666666; font-style: italic;">#   4 - unused</span>
    <span style="color: #666666; font-style: italic;">#   5 - X11</span>
    <span style="color: #666666; font-style: italic;">#   6 - reboot (Do NOT set initdefault to this)</span>
    <span style="color: #666666; font-style: italic;">#</span>
    id:<span style="color: #000000;">3</span>:initdefault:</pre></td></tr></table><p class="theCode" style="display:none;">[root@Mac /]$ vi /etc/inittab
    
    #
    # System initialization is started by /etc/init/rcS.conf
    #
    # Individual runlevels are started by /etc/init/rc.conf
    #
    # Ctrl-Alt-Delete is handled by /etc/init/control-alt-delete.conf
    #
    # Terminal gettys are handled by /etc/init/tty.conf and /etc/init/serial.conf,
    # with configuration in /etc/sysconfig/init.
    #
    # For information on how to write upstart event handlers, or how
    # upstart works, see init(5), init(8), and initctl(8).
    #
    # Default runlevel. The runlevels used are:
    #   0 - halt (Do NOT set initdefault to this)
    #   1 - Single user mode
    #   2 - Multiuser, without NFS (The same as 3, if you do not have networking)
    #   3 - Full multiuser mode
    #   4 - unused
    #   5 - X11
    #   6 - reboot (Do NOT set initdefault to this)
    #
    id:3:initdefault:</p></div>
    ";i:2;s:2893:"
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
    13
    14
    </pre></td><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #666666; font-style: italic;">#查看sshd服务的状态</span>
    <span style="color: #7a0874; font-weight: bold;">&#91;</span>root<span style="color: #000000; font-weight: bold;">@</span>mac <span style="color: #000000; font-weight: bold;">/</span><span style="color: #7a0874; font-weight: bold;">&#93;</span>$ service sshd status
    openssh-daemon is stopped
    &nbsp;
    <span style="color: #666666; font-style: italic;">#开启sshd服务</span>
    <span style="color: #7a0874; font-weight: bold;">&#91;</span>root<span style="color: #000000; font-weight: bold;">@</span>mac <span style="color: #000000; font-weight: bold;">/</span><span style="color: #7a0874; font-weight: bold;">&#93;</span>$ service sshd start
    Generating SSH2 RSA host key:                              <span style="color: #7a0874; font-weight: bold;">&#91;</span>  OK  <span style="color: #7a0874; font-weight: bold;">&#93;</span>
    Generating SSH1 RSA host key:                              <span style="color: #7a0874; font-weight: bold;">&#91;</span>  OK  <span style="color: #7a0874; font-weight: bold;">&#93;</span>
    Generating SSH2 DSA host key:                              <span style="color: #7a0874; font-weight: bold;">&#91;</span>  OK  <span style="color: #7a0874; font-weight: bold;">&#93;</span>
    Starting sshd:                                             <span style="color: #7a0874; font-weight: bold;">&#91;</span>  OK  <span style="color: #7a0874; font-weight: bold;">&#93;</span>
    &nbsp;
    <span style="color: #666666; font-style: italic;">#再确认一下状态，running状态说明启动成功</span>
    <span style="color: #7a0874; font-weight: bold;">&#91;</span>root<span style="color: #000000; font-weight: bold;">@</span>mac <span style="color: #000000; font-weight: bold;">/</span><span style="color: #7a0874; font-weight: bold;">&#93;</span>$ service sshd status
    openssh-daemon <span style="color: #7a0874; font-weight: bold;">&#40;</span>pid  <span style="color: #000000;">2027</span><span style="color: #7a0874; font-weight: bold;">&#41;</span> is running...</pre></td></tr></table><p class="theCode" style="display:none;">#查看sshd服务的状态
    [root@mac /]$ service sshd status
    openssh-daemon is stopped
    
    #开启sshd服务
    [root@mac /]$ service sshd start
    Generating SSH2 RSA host key:                              [  OK  ]
    Generating SSH1 RSA host key:                              [  OK  ]
    Generating SSH2 DSA host key:                              [  OK  ]
    Starting sshd:                                             [  OK  ]
    
    #再确认一下状态，running状态说明启动成功
    [root@mac /]$ service sshd status
    openssh-daemon (pid  2027) is running...</p></div>
    ";i:3;s:1649:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="line_numbers"><pre>1
    2
    3
    4
    5
    6
    </pre></td><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #666666; font-style: italic;">#通过chkconfig命令来设定开机自启动，默认为在2-5这4个启动级别上自动启动</span>
    <span style="color: #7a0874; font-weight: bold;">&#91;</span>root<span style="color: #000000; font-weight: bold;">@</span>Mac <span style="color: #000000; font-weight: bold;">/</span><span style="color: #7a0874; font-weight: bold;">&#93;</span>$ chkconfig sshd on
    &nbsp;
    <span style="color: #666666; font-style: italic;">#确认设定成功</span>
    <span style="color: #7a0874; font-weight: bold;">&#91;</span>root<span style="color: #000000; font-weight: bold;">@</span>Mac eric<span style="color: #7a0874; font-weight: bold;">&#93;</span>$ chkconfig <span style="color: #000000; font-weight: bold;">|</span> <span style="color: #c20cb9; font-weight: bold;">grep</span> sshd
    sshd           	<span style="color: #000000;">0</span>:off	<span style="color: #000000;">1</span>:off	<span style="color: #000000;">2</span>:on	<span style="color: #000000;">3</span>:on	<span style="color: #000000;">4</span>:on	<span style="color: #000000;">5</span>:on	<span style="color: #000000;">6</span>:off</pre></td></tr></table><p class="theCode" style="display:none;">#通过chkconfig命令来设定开机自启动，默认为在2-5这4个启动级别上自动启动
    [root@Mac /]$ chkconfig sshd on
    
    #确认设定成功
    [root@Mac eric]$ chkconfig | grep sshd
    sshd           	0:off	1:off	2:on	3:on	4:on	5:on	6:off</p></div>
    ";i:4;s:783:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="line_numbers"><pre>1
    2
    3
    </pre></td><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #666666; font-style: italic;">#IP地址可以在虚拟机里通过ifconfig命令获取</span>
    ericzhuの Macbook :~ $ <span style="color: #c20cb9; font-weight: bold;">ssh</span> root<span style="color: #000000; font-weight: bold;">@</span>10.211.55.8
    ssh: connect to host 10.211.55.8 port <span style="color: #000000;">22</span>: Connection refused</pre></td></tr></table><p class="theCode" style="display:none;">#IP地址可以在虚拟机里通过ifconfig命令获取
    ericzhuの Macbook :~ $ ssh root@10.211.55.8
    ssh: connect to host 10.211.55.8 port 22: Connection refused</p></div>
    ";i:5;s:2301:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="line_numbers"><pre>1
    2
    3
    4
    5
    6
    7
    8
    </pre></td><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #7a0874; font-weight: bold;">&#91;</span>root<span style="color: #000000; font-weight: bold;">@</span>Mac eric<span style="color: #7a0874; font-weight: bold;">&#93;</span>$ service iptables stop
    iptables: Flushing firewall rules:                         <span style="color: #7a0874; font-weight: bold;">&#91;</span>  OK  <span style="color: #7a0874; font-weight: bold;">&#93;</span>
    iptables: Setting chains to policy ACCEPT: filter          <span style="color: #7a0874; font-weight: bold;">&#91;</span>  OK  <span style="color: #7a0874; font-weight: bold;">&#93;</span>
    iptables: Unloading modules:                               <span style="color: #7a0874; font-weight: bold;">&#91;</span>  OK  <span style="color: #7a0874; font-weight: bold;">&#93;</span>
    &nbsp;
    <span style="color: #7a0874; font-weight: bold;">&#91;</span>root<span style="color: #000000; font-weight: bold;">@</span>Mac eric<span style="color: #7a0874; font-weight: bold;">&#93;</span>$ chkconfig iptables off
    <span style="color: #7a0874; font-weight: bold;">&#91;</span>root<span style="color: #000000; font-weight: bold;">@</span>Mac eric<span style="color: #7a0874; font-weight: bold;">&#93;</span>$ chkconfig <span style="color: #000000; font-weight: bold;">|</span> <span style="color: #c20cb9; font-weight: bold;">grep</span> iptables
    iptables       	<span style="color: #000000;">0</span>:off	<span style="color: #000000;">1</span>:off	<span style="color: #000000;">2</span>:off	<span style="color: #000000;">3</span>:off	<span style="color: #000000;">4</span>:off	<span style="color: #000000;">5</span>:off	<span style="color: #000000;">6</span>:off</pre></td></tr></table><p class="theCode" style="display:none;">[root@Mac eric]$ service iptables stop
    iptables: Flushing firewall rules:                         [  OK  ]
    iptables: Setting chains to policy ACCEPT: filter          [  OK  ]
    iptables: Unloading modules:                               [  OK  ]
    
    [root@Mac eric]$ chkconfig iptables off
    [root@Mac eric]$ chkconfig | grep iptables
    iptables       	0:off	1:off	2:off	3:off	4:off	5:off	6:off</p></div>
    ";i:6;s:2877:"
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
    13
    </pre></td><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #666666; font-style: italic;"># Firewall configuration written by system-config-firewall</span>
    <span style="color: #666666; font-style: italic;"># Manual customization of this file is not recommended.</span>
    <span style="color: #000000; font-weight: bold;">*</span>filter
    :INPUT ACCEPT <span style="color: #7a0874; font-weight: bold;">&#91;</span><span style="color: #000000;">0</span>:<span style="color: #000000;">0</span><span style="color: #7a0874; font-weight: bold;">&#93;</span>
    :FORWARD ACCEPT <span style="color: #7a0874; font-weight: bold;">&#91;</span><span style="color: #000000;">0</span>:<span style="color: #000000;">0</span><span style="color: #7a0874; font-weight: bold;">&#93;</span>
    :OUTPUT ACCEPT <span style="color: #7a0874; font-weight: bold;">&#91;</span><span style="color: #000000;">0</span>:<span style="color: #000000;">0</span><span style="color: #7a0874; font-weight: bold;">&#93;</span>
    <span style="color: #660033;">-A</span> INPUT <span style="color: #660033;">-m</span> state <span style="color: #660033;">--state</span> ESTABLISHED,RELATED <span style="color: #660033;">-j</span> ACCEPT
    <span style="color: #660033;">-A</span> INPUT <span style="color: #660033;">-p</span> icmp <span style="color: #660033;">-j</span> ACCEPT
    <span style="color: #660033;">-A</span> INPUT <span style="color: #660033;">-i</span> lo <span style="color: #660033;">-j</span> ACCEPT
    <span style="color: #660033;">-A</span> INPUT <span style="color: #660033;">-m</span> state <span style="color: #660033;">--state</span> NEW <span style="color: #660033;">-m</span> tcp <span style="color: #660033;">-p</span> tcp <span style="color: #660033;">--dport</span> <span style="color: #000000;">22</span> <span style="color: #660033;">-j</span> ACCEPT
    <span style="color: #660033;">-A</span> INPUT <span style="color: #660033;">-j</span> REJECT <span style="color: #660033;">--reject-with</span> icmp-host-prohibited
    <span style="color: #660033;">-A</span> FORWARD <span style="color: #660033;">-j</span> REJECT <span style="color: #660033;">--reject-with</span> icmp-host-prohibited
    COMMIT</pre></td></tr></table><p class="theCode" style="display:none;"># Firewall configuration written by system-config-firewall
    # Manual customization of this file is not recommended.
    *filter
    :INPUT ACCEPT [0:0]
    :FORWARD ACCEPT [0:0]
    :OUTPUT ACCEPT [0:0]
    -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
    -A INPUT -p icmp -j ACCEPT
    -A INPUT -i lo -j ACCEPT
    -A INPUT -m state --state NEW -m tcp -p tcp --dport 22 -j ACCEPT
    -A INPUT -j REJECT --reject-with icmp-host-prohibited
    -A FORWARD -j REJECT --reject-with icmp-host-prohibited
    COMMIT</p></div>
    ";i:7;s:1811:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="line_numbers"><pre>1
    2
    3
    4
    5
    6
    </pre></td><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #7a0874; font-weight: bold;">&#91;</span>root<span style="color: #000000; font-weight: bold;">@</span>Mac eric<span style="color: #7a0874; font-weight: bold;">&#93;</span>$ service iptables restart
    iptables: Flushing firewall rules:                         <span style="color: #7a0874; font-weight: bold;">&#91;</span>  OK  <span style="color: #7a0874; font-weight: bold;">&#93;</span>
    iptables: Setting chains to policy ACCEPT: filter          <span style="color: #7a0874; font-weight: bold;">&#91;</span>  OK  <span style="color: #7a0874; font-weight: bold;">&#93;</span>
    iptables: Unloading modules:                               <span style="color: #7a0874; font-weight: bold;">&#91;</span>  OK  <span style="color: #7a0874; font-weight: bold;">&#93;</span>
    iptables: Applying firewall rules:                         <span style="color: #7a0874; font-weight: bold;">&#91;</span>  OK  <span style="color: #7a0874; font-weight: bold;">&#93;</span>
    <span style="color: #7a0874; font-weight: bold;">&#91;</span>root<span style="color: #000000; font-weight: bold;">@</span>Mac eric<span style="color: #7a0874; font-weight: bold;">&#93;</span><span style="color: #666666; font-style: italic;">#</span></pre></td></tr></table><p class="theCode" style="display:none;">[root@Mac eric]$ service iptables restart
    iptables: Flushing firewall rules:                         [  OK  ]
    iptables: Setting chains to policy ACCEPT: filter          [  OK  ]
    iptables: Unloading modules:                               [  OK  ]
    iptables: Applying firewall rules:                         [  OK  ]
    [root@Mac eric]#</p></div>
    ";i:8;s:459:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="line_numbers"><pre>1
    </pre></td><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #7a0874; font-weight: bold;">alias</span> <span style="color: #007800;">fedora</span>=<span style="color: #ff0000;">'ssh root@虚拟机IP地址'</span></pre></td></tr></table><p class="theCode" style="display:none;">alias fedora='ssh root@虚拟机IP地址'</p></div>
    ";}
categories:
  - Mac学习
tags:
  - fedora
  - Linux
  - mac
  - parallels
  - ssh
  - 虚拟机

---
自从买了Macbook之后一直在学习Unix命令行，目的之一是为了更熟练地玩Liunx系统。虽然[Mac OS X和Linux都是基于Unix][1]，但是Mac OS X在各种设定上还是和主流Linux有很大区别，所以最终还是在Parallels里面安装了Ret Hat旗下的[Fedora][2]（因为它和RHEL有很多共通的地方）。既然要学命令行式的操作方式，那默认启动的X对我来说就是徒占系统资源而已，毫无意义，所以想到直接在Mac OS X的Terminal里SSH连接到Fedora虚拟机，这样一来能够节省系统资源，二来不用在虚拟机和本机之间切换，省去很多麻烦，三来可以让自己习惯命令行的操作方式，一举多得。
  
<!--more-->

<div style="width: 610px" class="wp-caption alignnone">
  <img title="X模式和文本模式下的Fedora虚拟机系统资源占用对比" src="https://www.digglife.net/wp-content/uploads/2011/05/parallels-vm-memory.png" alt="X模式和文本模式下的Fedora虚拟机系统资源占用对比" width="600" height="457" />
  
  <p class="wp-caption-text">
    X模式和文本模式下的Fedora虚拟机系统资源占用对比
  </p>
</div>

Parallels虚拟机的默认网络设定是[Shared Networking][3]，在这种模式下，主机和虚拟机之间能够通过虚拟网络互相通信，虚拟机也能通过主机连接互联网，所以其实在本机不需要任何设定就可以连接到虚拟机。事实上，我们通过ifconfig命令就会发现，Parallels在本地建立了两个虚拟网卡，vnic0和vnic1，前者用于Shared Networking，后者用于Host-Only模式。
  
<img class="aligncenter size-full wp-image-3082" title="Parallels的shared-networking模式" src="https://www.digglife.net/wp-content/uploads/2011/05/shared-networking.png" alt="Parallels的shared-networking模式" width="593" height="260" />
  
所以要实现SSH连接到Linux虚拟机，只需要在Linux下做一些设定即可。

### 设定Fedora默认启动为文本模式（可选）

Linux一般有0-6一共7种启动级别，默认为5，即图形界面模式，可以通过编辑/etc/inittab文件的方式更改。这个文件事实上也只有最后一行有效，其他全是注释。

#我把Root用户的命令提示符全部更换成了美元符号，不然命令会被错误地识别为注释了。

<pre lang="bash" line="1">[root@Mac /]$ vi /etc/inittab

#
# System initialization is started by /etc/init/rcS.conf
#
# Individual runlevels are started by /etc/init/rc.conf
#
# Ctrl-Alt-Delete is handled by /etc/init/control-alt-delete.conf
#
# Terminal gettys are handled by /etc/init/tty.conf and /etc/init/serial.conf,
# with configuration in /etc/sysconfig/init.
#
# For information on how to write upstart event handlers, or how
# upstart works, see init(5), init(8), and initctl(8).
#
# Default runlevel. The runlevels used are:
#   0 - halt (Do NOT set initdefault to this)
#   1 - Single user mode
#   2 - Multiuser, without NFS (The same as 3, if you do not have networking)
#   3 - Full multiuser mode
#   4 - unused
#   5 - X11
#   6 - reboot (Do NOT set initdefault to this)
#
id:3:initdefault:</pre>

编辑保存之后，下次重启就会启动到文本界面了。

### 开启SSH服务，并设定为开机自启动

Fedora下SSH服务默认是停止的，所以我们需要手动开启。

<pre lang="bash" line="1">#查看sshd服务的状态
[root@mac /]$ service sshd status
openssh-daemon is stopped

#开启sshd服务
[root@mac /]$ service sshd start
Generating SSH2 RSA host key:                              [  OK  ]
Generating SSH1 RSA host key:                              [  OK  ]
Generating SSH2 DSA host key:                              [  OK  ]
Starting sshd:                                             [  OK  ]

#再确认一下状态，running状态说明启动成功
[root@mac /]$ service sshd status
openssh-daemon (pid  2027) is running...</pre>

每次手动开启就太麻烦了，所以可以将SSH服务设置为开机自启动

<pre lang="bash" line="1">#通过chkconfig命令来设定开机自启动，默认为在2-5这4个启动级别上自动启动
[root@Mac /]$ chkconfig sshd on

#确认设定成功
[root@Mac eric]$ chkconfig | grep sshd
sshd           	0:off	1:off	2:on	3:on	4:on	5:on	6:off</pre>

### 更改防火墙设定

Fedora的防火墙在手动配置之前是拒绝ssh连接的，所以即便是开启了ssh服务，我从本地连接也会提示Connection Refused。

<pre lang="bash" line="1">#IP地址可以在虚拟机里通过ifconfig命令获取
ericzhuの Macbook :~ $ ssh root@10.211.55.8
ssh: connect to host 10.211.55.8 port 22: Connection refused</pre>

解决办法有两个：

  1. 完全禁用防火墙
最省心的办法，本来这个防火墙也没有太大作用。方法和处理SSH服务的类似。

<pre lang="bash" line="1">[root@Mac eric]$ service iptables stop
iptables: Flushing firewall rules:                         [  OK  ]
iptables: Setting chains to policy ACCEPT: filter          [  OK  ]
iptables: Unloading modules:                               [  OK  ]

[root@Mac eric]$ chkconfig iptables off
[root@Mac eric]$ chkconfig | grep iptables
iptables       	0:off	1:off	2:off	3:off	4:off	5:off	6:off</pre>

  2. 配置iptables文件，允许SSH连接
如果觉得禁用防火墙太暴力，可以配置一下防火墙设定，让它允许ssh连接。Fedora提供了一个图形配置界面[system-config-firewall][4]，在文本模式下直接输入system-config-firewall即可进入配置界面，进入Custom选项之后，在Trust Services列表里勾选SSH，然后应用即可。
  
<img class="alignnone size-full wp-image-3084" title="system-config-firewall配置界面" src="https://www.digglife.net/wp-content/uploads/2011/05/system-config-firewall.png" alt="配置防火墙的图形界面system-config-firewall" width="600" height="359" />

当然，system-config-firewall也仅仅是一个用来向/etc/sysconfig/iptables写入数据的工具，我们可以直接修改iptables文件，手动加入防火墙规则，然后重启iptables服务即可。

第10行就是允许SSH连接的规则（SSH默认端口22）。

<pre lang="bash" line="1"># Firewall configuration written by system-config-firewall
# Manual customization of this file is not recommended.
*filter
:INPUT ACCEPT [0:0]
:FORWARD ACCEPT [0:0]
:OUTPUT ACCEPT [0:0]
-A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
-A INPUT -p icmp -j ACCEPT
-A INPUT -i lo -j ACCEPT
-A INPUT -m state --state NEW -m tcp -p tcp --dport 22 -j ACCEPT
-A INPUT -j REJECT --reject-with icmp-host-prohibited
-A FORWARD -j REJECT --reject-with icmp-host-prohibited
COMMIT</pre>

保存之后，重启防火墙服务

<pre lang="bash" line="1">[root@Mac eric]$ service iptables restart
iptables: Flushing firewall rules:                         [  OK  ]
iptables: Setting chains to policy ACCEPT: filter          [  OK  ]
iptables: Unloading modules:                               [  OK  ]
iptables: Applying firewall rules:                         [  OK  ]
[root@Mac eric]#</pre>

### 在终端里SSH登陆到虚拟机

这样一切配置妥当之后，在终端里就能ssh登陆到Linux虚拟机了。为了以后方便，我在.bashrc里写入一笔别名：

<pre lang="bash" line="1">alias fedora='ssh root@虚拟机IP地址'</pre>

以后启动虚拟机之后，直接输入fedora然后输入密码即可登入。

<img class="alignnone size-full wp-image-3085" title="从Mac终端登入Fedora虚拟机" src="https://www.digglife.net/wp-content/uploads/2011/05/ssh-login-linux-vm.png" alt="从Mac终端登入Fedora虚拟机" width="600" height="488" />

### 杂七杂八

[Parallels还支持Bridge Networking][5]（网络桥接），采用这种模式的时候，虚拟机可以模拟成本地网络中的机器，和本机平行。我在家使用无线路由器，所以虚拟机的IP就会变成192.168.0.X，这种方式也许比Shared Networking更加直观。

和[Ubuntu][6]不同，Fedora（Red Hat系的Linux应该都这样）默认启用了root账号，而在安装过程中新建的用户账号是没有sudo权限的，也就是说，如果要执行某些系统管理命令，必须切换到root，而不能使用sudo，这和我以前在Ubuntu下养成的习惯不同。
  
可以通过visudo命令将自己的账户加入到sudoer。

Fedora 15也即将推出了，好像是要加入到 GNOME 3，很牛掰的样子。

 [1]: http://www.apple.com.cn/macosx/what-is-macosx/core-foundation.html
 [2]: http://fedoraproject.org/
 [3]: http://download.parallels.com/desktop/v4/docs/en/Parallels_Desktop_Users_Guide/22247.htm
 [4]: http://fedoraproject.org/wiki/SystemConfig/firewall
 [5]: http://download.parallels.com/desktop/v4/docs/en/Parallels_Desktop_Users_Guide/22251.htm
 [6]: https://www.digglife.net/articles/category/about_ubuntu
