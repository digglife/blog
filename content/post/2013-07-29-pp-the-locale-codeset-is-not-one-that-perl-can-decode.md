---
title: PP打包Perl脚本出现编码集错误的解决
author: 摩摩诘
type: post
date: 2013-07-28T17:24:25+00:00
excerpt: "前些天写了一个通过HTTP API 读取公司LDAP信息，并写入到数据库的Perl脚本。因为希望做到在没有Perl环境的Windows Server上都能运行，于是尝试了用社区神器PP(Par::Packer)打包成exe。打包结果除了文件大小之外很令人满意，在本机上测试也完全没有问题，但令人沮丧的是，在某些Server上测试的时候出现The locale codeset(CPxxx) isn't one that perl can decode错误，Stackoverflow 和 PerlMonk 上都没有人解释出现这个问题的原因，也没有提供一个理性的解决方案，于是仔细研究了一下。"
url: /articles/pp-the-locale-codeset-is-not-one-that-perl-can-decode.html
index_image:
  - https://www.digglife.net/wp-content/uploads/2013/07/perl.png
views:
  - 521
duoshuo_thread_id:
  - 1154125469839261839
wp-syntax-cache-content:
  - |
    a:3:{i:1;s:931:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="line_numbers"><pre>1
    2
    3
    4
    </pre></td><td class="code"><pre class="winbatch" style="font-family:monospace;">The locale codeset <span style="color: #66cc66;">&#40;</span>cp936<span style="color: #66cc66;">&#41;</span> isn<span style="color: #ff0000;">'t one that perl can decode, stopped at Encode/Locale.pm line 94.
    Compilation failed in require at LWP/UserAgent.pm line 1001.
    Compilation failed in require at script/bpinfo.pl line 2.
    BEGIN failed--compilation aborted at script/bpinfo.pl line 2.</span></pre></td></tr></table><p class="theCode" style="display:none;">The locale codeset (cp936) isn't one that perl can decode, stopped at Encode/Locale.pm line 94.
    Compilation failed in require at LWP/UserAgent.pm line 1001.
    Compilation failed in require at script/bpinfo.pl line 2.
    BEGIN failed--compilation aborted at script/bpinfo.pl line 2.</p></div>
    ";i:2;s:7401:"
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
    26
    27
    </pre></td><td class="code"><pre class="perl" style="font-family:monospace;"><span style="color: #000000; font-weight: bold;">sub</span> env_proxy <span style="color: #009900;">&#123;</span>
        <span style="color: #b1b100;">my</span> <span style="color: #009900;">&#40;</span><span style="color: #0000ff;">$self</span><span style="color: #009900;">&#41;</span> <span style="color: #339933;">=</span> <span style="color: #0000ff;">@_</span><span style="color: #339933;">;</span>
        <span style="color: #000066;">require</span> Encode<span style="color: #339933;">;</span>
        <span style="color: #000066;">require</span> Encode<span style="color: #339933;">::</span><span style="color: #006600;">Locale</span><span style="color: #339933;">;</span>
        <span style="color: #b1b100;">my</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">$k</span><span style="color: #339933;">,</span><span style="color: #0000ff;">$v</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
        <span style="color: #b1b100;">while</span><span style="color: #009900;">&#40;</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">$k</span><span style="color: #339933;">,</span> <span style="color: #0000ff;">$v</span><span style="color: #009900;">&#41;</span> <span style="color: #339933;">=</span> <span style="color: #000066;">each</span> <span style="color: #0000ff;">%ENV</span><span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span>
    	<span style="color: #b1b100;">if</span> <span style="color: #009900;">&#40;</span><span style="color: #0000ff;">$ENV</span><span style="color: #009900;">&#123;</span>REQUEST_METHOD<span style="color: #009900;">&#125;</span><span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span>
    	    <span style="color: #666666; font-style: italic;"># Need to be careful when called in the CGI environment, as</span>
    	    <span style="color: #666666; font-style: italic;"># the HTTP_PROXY variable is under control of that other guy.</span>
    	    <span style="color: #b1b100;">next</span> <span style="color: #b1b100;">if</span> <span style="color: #0000ff;">$k</span> <span style="color: #339933;">=~</span> <span style="color: #009966; font-style: italic;">/^HTTP_/</span><span style="color: #339933;">;</span>
    	    <span style="color: #0000ff;">$k</span> <span style="color: #339933;">=</span> <span style="color: #ff0000;">&quot;HTTP_PROXY&quot;</span> <span style="color: #b1b100;">if</span> <span style="color: #0000ff;">$k</span> <span style="color: #b1b100;">eq</span> <span style="color: #ff0000;">&quot;CGI_HTTP_PROXY&quot;</span><span style="color: #339933;">;</span>
    	<span style="color: #009900;">&#125;</span>
    	<span style="color: #0000ff;">$k</span> <span style="color: #339933;">=</span> <span style="color: #000066;">lc</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">$k</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    	<span style="color: #b1b100;">next</span> <span style="color: #b1b100;">unless</span> <span style="color: #0000ff;">$k</span> <span style="color: #339933;">=~</span> <span style="color: #009966; font-style: italic;">/^(.*)_proxy$/</span><span style="color: #339933;">;</span>
    	<span style="color: #0000ff;">$k</span> <span style="color: #339933;">=</span> <span style="color: #0000ff;">$1</span><span style="color: #339933;">;</span>
    	<span style="color: #b1b100;">if</span> <span style="color: #009900;">&#40;</span><span style="color: #0000ff;">$k</span> <span style="color: #b1b100;">eq</span> <span style="color: #ff0000;">'no'</span><span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span>
    	    <span style="color: #0000ff;">$self</span><span style="color: #339933;">-&amp;</span><span style="color: #b1b100;">gt</span><span style="color: #339933;">;</span>no_proxy<span style="color: #009900;">&#40;</span><span style="color: #000066;">split</span><span style="color: #009900;">&#40;</span><span style="color: #009966; font-style: italic;">/\s*,\s*/</span><span style="color: #339933;">,</span> <span style="color: #0000ff;">$v</span><span style="color: #009900;">&#41;</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    	<span style="color: #009900;">&#125;</span>
    	<span style="color: #b1b100;">else</span> <span style="color: #009900;">&#123;</span>
                <span style="color: #666666; font-style: italic;"># Ignore random _proxy variables, allow only valid schemes</span>
                <span style="color: #b1b100;">next</span> <span style="color: #b1b100;">unless</span> <span style="color: #0000ff;">$k</span> <span style="color: #339933;">=~</span> <span style="color: #009966; font-style: italic;">/^$URI::scheme_re\z/</span><span style="color: #339933;">;</span>
                <span style="color: #666666; font-style: italic;"># Ignore xxx_proxy variables if xxx isn't a supported protocol</span>
                <span style="color: #b1b100;">next</span> <span style="color: #b1b100;">unless</span> LWP<span style="color: #339933;">::</span><span style="color: #006600;">Protocol</span><span style="color: #339933;">::</span><span style="color: #006600;">implementor</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">$k</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    	    <span style="color: #0000ff;">$self</span><span style="color: #339933;">-&gt;</span><span style="color: #006600;">proxy</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">$k</span><span style="color: #339933;">,</span> Encode<span style="color: #339933;">::</span><span style="color: #006600;">decode</span><span style="color: #009900;">&#40;</span>locale <span style="color: #339933;">=&amp;</span><span style="color: #b1b100;">gt</span><span style="color: #339933;">;</span> <span style="color: #0000ff;">$v</span><span style="color: #009900;">&#41;</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    	<span style="color: #009900;">&#125;</span>
        <span style="color: #009900;">&#125;</span>
    <span style="color: #009900;">&#125;</span></pre></td></tr></table><p class="theCode" style="display:none;">sub env_proxy {
        my ($self) = @_;
        require Encode;
        require Encode::Locale;
        my($k,$v);
        while(($k, $v) = each %ENV) {
    	if ($ENV{REQUEST_METHOD}) {
    	    # Need to be careful when called in the CGI environment, as
    	    # the HTTP_PROXY variable is under control of that other guy.
    	    next if $k =~ /^HTTP_/;
    	    $k = &quot;HTTP_PROXY&quot; if $k eq &quot;CGI_HTTP_PROXY&quot;;
    	}
    	$k = lc($k);
    	next unless $k =~ /^(.*)_proxy$/;
    	$k = $1;
    	if ($k eq 'no') {
    	    $self-&amp;gt;no_proxy(split(/\s*,\s*/, $v));
    	}
    	else {
                # Ignore random _proxy variables, allow only valid schemes
                next unless $k =~ /^$URI::scheme_re\z/;
                # Ignore xxx_proxy variables if xxx isn't a supported protocol
                next unless LWP::Protocol::implementor($k);
    	    $self-&gt;proxy($k, Encode::decode(locale =&amp;gt; $v));
    	}
        }
    }</p></div>
    ";i:3;s:7317:"
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
    26
    27
    28
    29
    30
    31
    </pre></td><td class="code"><pre class="perl" style="font-family:monospace;"><span style="color: #b1b100;">if</span> <span style="color: #009900;">&#40;</span><span style="color: #0000ff;">$^O</span> <span style="color: #b1b100;">eq</span> <span style="color: #ff0000;">&quot;MSWin32&quot;</span><span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span>
    	<span style="color: #b1b100;">unless</span> <span style="color: #009900;">&#40;</span><span style="color: #0000ff;">$ENCODING_LOCALE</span><span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span>
    	    <span style="color: #666666; font-style: italic;"># Try to obtain what the Windows ANSI code page is</span>
    	    <span style="color: #000066;">eval</span> <span style="color: #009900;">&#123;</span>
    		<span style="color: #b1b100;">unless</span> <span style="color: #009900;">&#40;</span><span style="color: #000066;">defined</span> <span style="color: #0000ff;">&amp;GetACP</span><span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span>
    		    <span style="color: #000066;">require</span> Win32<span style="color: #339933;">::</span><span style="color: #006600;">API</span><span style="color: #339933;">;</span>
    		    Win32<span style="color: #339933;">::</span><span style="color: #006600;">API</span><span style="color: #339933;">-&gt;</span><span style="color: #006600;">Import</span><span style="color: #009900;">&#40;</span><span style="color: #ff0000;">'kernel32'</span><span style="color: #339933;">,</span> <span style="color: #ff0000;">'int GetACP()'</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    		<span style="color: #009900;">&#125;</span><span style="color: #339933;">;</span>
    		<span style="color: #b1b100;">if</span> <span style="color: #009900;">&#40;</span><span style="color: #000066;">defined</span> <span style="color: #0000ff;">&amp;amp</span><span style="color: #339933;">;</span>GetACP<span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span>
    		    <span style="color: #b1b100;">my</span> <span style="color: #0000ff;">$cp</span> <span style="color: #339933;">=</span> GetACP<span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    		    <span style="color: #0000ff;">$ENCODING_LOCALE</span> <span style="color: #339933;">=</span> <span style="color: #ff0000;">&quot;cp$cp&quot;</span> <span style="color: #b1b100;">if</span> <span style="color: #0000ff;">$cp</span><span style="color: #339933;">;</span>
    		<span style="color: #009900;">&#125;</span>
    	    <span style="color: #009900;">&#125;</span><span style="color: #339933;">;</span>
    	<span style="color: #009900;">&#125;</span>
    &nbsp;
    	<span style="color: #b1b100;">unless</span> <span style="color: #009900;">&#40;</span><span style="color: #0000ff;">$ENCODING_CONSOLE_IN</span><span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span>
    	    <span style="color: #666666; font-style: italic;"># If we have the Win32::Console module installed we can ask</span>
    	    <span style="color: #666666; font-style: italic;"># it for the code set to use</span>
    	    <span style="color: #000066;">eval</span> <span style="color: #009900;">&#123;</span>
    		<span style="color: #000066;">require</span> Win32<span style="color: #339933;">::</span><span style="color: #006600;">Console</span><span style="color: #339933;">;</span>
    		<span style="color: #b1b100;">my</span> <span style="color: #0000ff;">$cp</span> <span style="color: #339933;">=</span> Win32<span style="color: #339933;">::</span><span style="color: #006600;">Console</span><span style="color: #339933;">::</span><span style="color: #006600;">InputCP</span><span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    		<span style="color: #0000ff;">$ENCODING_CONSOLE_IN</span> <span style="color: #339933;">=</span> <span style="color: #ff0000;">&quot;cp$cp&quot;</span> <span style="color: #b1b100;">if</span> <span style="color: #0000ff;">$cp</span><span style="color: #339933;">;</span>
    		<span style="color: #0000ff;">$cp</span> <span style="color: #339933;">=</span> Win32<span style="color: #339933;">::</span><span style="color: #006600;">Console</span><span style="color: #339933;">::</span><span style="color: #006600;">OutputCP</span><span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    		<span style="color: #0000ff;">$ENCODING_CONSOLE_OUT</span> <span style="color: #339933;">=</span> <span style="color: #ff0000;">&quot;cp$cp&quot;</span> <span style="color: #b1b100;">if</span> <span style="color: #0000ff;">$cp</span><span style="color: #339933;">;</span>
    	    <span style="color: #009900;">&#125;</span><span style="color: #339933;">;</span>
    	    <span style="color: #666666; font-style: italic;"># Invoking the 'chcp' program might also work</span>
    	    <span style="color: #b1b100;">if</span> <span style="color: #009900;">&#40;</span><span style="color: #339933;">!</span><span style="color: #0000ff;">$ENCODING_CONSOLE_IN</span> <span style="color: #339933;">&amp;&amp;</span> <span style="color: #009900;">&#40;</span><span style="color: #000066;">qx</span><span style="color: #009900;">&#40;</span>chcp<span style="color: #009900;">&#41;</span> <span style="color: #339933;">||</span> <span style="color: #ff0000;">''</span><span style="color: #009900;">&#41;</span> <span style="color: #339933;">=~</span> <span style="color: #009966; font-style: italic;">/^Active code page: (\d+)/</span><span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span>
    		<span style="color: #0000ff;">$ENCODING_CONSOLE_IN</span> <span style="color: #339933;">=</span> <span style="color: #ff0000;">&quot;cp$1&quot;</span><span style="color: #339933;">;</span>
    	    <span style="color: #009900;">&#125;</span>
    	<span style="color: #009900;">&#125;</span>
        <span style="color: #009900;">&#125;</span></pre></td></tr></table><p class="theCode" style="display:none;">if ($^O eq &quot;MSWin32&quot;) {
    	unless ($ENCODING_LOCALE) {
    	    # Try to obtain what the Windows ANSI code page is
    	    eval {
    		unless (defined &amp;GetACP) {
    		    require Win32::API;
    		    Win32::API-&gt;Import('kernel32', 'int GetACP()');
    		};
    		if (defined &amp;amp;GetACP) {
    		    my $cp = GetACP();
    		    $ENCODING_LOCALE = &quot;cp$cp&quot; if $cp;
    		}
    	    };
    	}
    
    	unless ($ENCODING_CONSOLE_IN) {
    	    # If we have the Win32::Console module installed we can ask
    	    # it for the code set to use
    	    eval {
    		require Win32::Console;
    		my $cp = Win32::Console::InputCP();
    		$ENCODING_CONSOLE_IN = &quot;cp$cp&quot; if $cp;
    		$cp = Win32::Console::OutputCP();
    		$ENCODING_CONSOLE_OUT = &quot;cp$cp&quot; if $cp;
    	    };
    	    # Invoking the 'chcp' program might also work
    	    if (!$ENCODING_CONSOLE_IN &amp;&amp; (qx(chcp) || '') =~ /^Active code page: (\d+)/) {
    		$ENCODING_CONSOLE_IN = &quot;cp$1&quot;;
    	    }
    	}
        }</p></div>
    ";}
categories:
  - 代码卷轴
tags:
  - par-packer
  - perl
  - pp

---
前些天写了一个通过HTTP API 读取公司LDAP信息，并写入到数据库的Perl脚本。因为希望做到在没有Perl环境的Windows Server上都能运行，于是尝试用社区神器PP(<a title="Par-Packer" href="http://search.cpan.org/~rschupp/PAR-Packer-1.014/lib/pp.pm" target="_blank">Par::Packer</a>)打包成exe。

<!--more-->

打包结果很令人满意，在本机上测试也完全没有问题，但令人沮丧的是，在某些Server上测试的时候出现The locale codeset(CPxxx) isn&#8217;t one that perl can decode错误。

可能因为出现这个问题的概率比较小，Stackoverflow 和 PerlMonk 上都没有人解释出现这个问题的原因，也没有提供一个理性的解决方案，于是仔细研究了一下，发现了一些PP的Tutorial上没有讲清楚的特性。

打包所在机器的环境

  * OS：Windows 2003 SP2 32bit English
  * Perl环境：StrawBerry 5.16.3.1
  * PP版本：1.014

某测试机运行时的错误信息：

<pre lang="winbatch" line="1">The locale codeset (cp936) isn't one that perl can decode, stopped at Encode/Locale.pm line 94.
Compilation failed in require at LWP/UserAgent.pm line 1001.
Compilation failed in require at script/bpinfo.pl line 2.
BEGIN failed--compilation aborted at script/bpinfo.pl line 2.</pre>

提示信息的意思很清楚，Perl的Encode::Locale模块无法解码CP936（简体中文）编码集，而且和<a title="LWP::UserAgent" href="http://search.cpan.org/~gaas/libwww-perl-6.05/lib/LWP/UserAgent.pm" target="_blank">LWP::UserAgent</a>|<a title="Encode::Locale" href="http://search.cpan.org/~gaas/Encode-Locale-1.03/lib/Encode/Locale.pm" target="_blank">Encode::Locale</a>模块相关。仔细看了一下代码之后发现调用关系是这样的：

我要通过公司内部的HTTP API获取JSON数据并解析，所以用到了 <a title="LWP::Simple" href="http://search.cpan.org/~gaas/libwww-perl-6.05/lib/LWP/Simple.pm" target="_blank">LWP::Simple</a> 这个模块，LWP::Simple调用了 LWP::UserAgent 中的 env_proxy，而该方法会在**运行时**调用Encode::Locale分析环境变量字符的编码，然后通过Encode::decode解码。

但是事实上Encode模块是完全能够解码cp936的，那为什么会出现这种错误呢?

分析了以后发现了症结在于，Encode::Locale是在<span style="color: #ff0000;"><strong>运行时</strong></span>调用的，如果在Windows平台上运行，会通过chcp命令获取当前的编码集设定，而P在打包时如果使用了-x参数，pp会在运行时分析需要的模块并打包。这样，如果在cp1252（拉丁文编码集）的环境下运行pp，Encode中用于decode简体中文的模块（Encode::CN）就不会被打包。所以生成的exe文件在正常的简体中文Windows下会在运行的时候获取到cp936编码集，但是无法Decode。

LWP::UserAgent->env_proxy 方法：

<pre lang="perl" line="1">sub env_proxy {
    my ($self) = @_;
    require Encode;
    require Encode::Locale;
    my($k,$v);
    while(($k, $v) = each %ENV) {
	if ($ENV{REQUEST_METHOD}) {
	    # Need to be careful when called in the CGI environment, as
	    # the HTTP_PROXY variable is under control of that other guy.
	    next if $k =~ /^HTTP_/;
	    $k = "HTTP_PROXY" if $k eq "CGI_HTTP_PROXY";
	}
	$k = lc($k);
	next unless $k =~ /^(.*)_proxy$/;
	$k = $1;
	if ($k eq 'no') {
	    $self-&gt;no_proxy(split(/\s*,\s*/, $v));
	}
	else {
            # Ignore random _proxy variables, allow only valid schemes
            next unless $k =~ /^$URI::scheme_re\z/;
            # Ignore xxx_proxy variables if xxx isn't a supported protocol
            next unless LWP::Protocol::implementor($k);
	    $self->proxy($k, Encode::decode(locale =&gt; $v));
	}
    }
}</pre>

Encode::Locale初始化时用于获取Windows编码集的代码片段：

<pre lang="perl" line="1">if ($^O eq "MSWin32") {
	unless ($ENCODING_LOCALE) {
	    # Try to obtain what the Windows ANSI code page is
	    eval {
		unless (defined &GetACP) {
		    require Win32::API;
		    Win32::API->Import('kernel32', 'int GetACP()');
		};
		if (defined &GetACP) {
		    my $cp = GetACP();
		    $ENCODING_LOCALE = "cp$cp" if $cp;
		}
	    };
	}

	unless ($ENCODING_CONSOLE_IN) {
	    # If we have the Win32::Console module installed we can ask
	    # it for the code set to use
	    eval {
		require Win32::Console;
		my $cp = Win32::Console::InputCP();
		$ENCODING_CONSOLE_IN = "cp$cp" if $cp;
		$cp = Win32::Console::OutputCP();
		$ENCODING_CONSOLE_OUT = "cp$cp" if $cp;
	    };
	    # Invoking the 'chcp' program might also work
	    if (!$ENCODING_CONSOLE_IN && (qx(chcp) || '') =~ /^Active code page: (\d+)/) {
		$ENCODING_CONSOLE_IN = "cp$1";
	    }
	}
    }</pre>

想到的解决办法有2个：

  1. 用-a参数将整个Encode模块都打包进去。（测试不可行）
  2. 弃用LWP::Simple，直接 use LWP::UserAgent，且不调用env_proxy方法。

第一个方法经过测试之后发现不可行，原因也很简单，pp打包时根据需要生成了几个和encode相关的dll文件，于是在其他机器上运行时，真正起作用的时那几个dll，所以依然会出错。

第二个方法测试可行。虽然这样无法获取系统的代理设置（LWP::Simple则默认调用env_proxy），但是需要从环境变量中获取代理设定的情况几乎没有，所以可以说没有影响。

据说一些匿名和尚说，使用ActiveState家的PDK打包不会出现这种错误，但是这货卖几百美刀，实在太贵，我也不想用破解版，何况还是搞清楚问题的来龙去脉比较好。

PP这个玩意虽然很神，但是问题不少，比如它虽然提供了一个给exe加图标的选项，但是我用的时候会报The system cannot execute the specified program错误，最后发现它只支持单一分辨率的icon（比如32bit 16&#215;16），使用内置多种格式的icon就会报错，这一点也浪费了我不少时间。

<div id="xunlei_com_thunder_helper_plugin_d462f475-c18e-46be-bd10-327458d045bd">
</div>

<div id="xunlei_com_thunder_helper_plugin_d462f475-c18e-46be-bd10-327458d045bd">
</div>

<div id="xunlei_com_thunder_helper_plugin_d462f475-c18e-46be-bd10-327458d045bd">
</div>

<div id="xunlei_com_thunder_helper_plugin_d462f475-c18e-46be-bd10-327458d045bd">
</div>