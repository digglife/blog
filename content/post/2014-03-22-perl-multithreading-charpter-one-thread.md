---
title: Perl的多线程应用之一:内置Thread模块
author: 摩摩诘
type: post
date: 2014-03-21T16:21:01+00:00
excerpt: 前些日子在写一些 Perl 脚本的时候为了追求处理速度或者时间上的平行，频繁地使用到了 Perl 的多线程功能。Perl 内置有一个多线程模块 Thread ，提供了常规意义上的 multithreads 功能，可以满足我们的一般需求。
url: /articles/perl-multithreading-charpter-one-thread.html
index_image:
  - https://www.digglife.net/wp-content/uploads/2014/03/perl-threads.jpg
duoshuo_thread_id:
  - 1154125469839262179
views:
  - 1135
wp-syntax-cache-content:
  - |
    a:1:{i:1;s:6516:"
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
    </pre></td><td class="code"><pre class="perl" style="font-family:monospace;">    <span style="color: #b1b100;">my</span> <span style="color: #0000ff;">@threads</span><span style="color: #339933;">;</span>
        <span style="color: #b1b100;">my</span> <span style="color: #0000ff;">@snips</span> <span style="color: #339933;">=</span> <span style="color: #000066;">split</span> <span style="color: #009966; font-style: italic;">/,/</span><span style="color: #339933;">,</span><span style="color: #0000ff;">$opts</span><span style="color: #009900;">&#123;</span>dest<span style="color: #009900;">&#125;</span><span style="color: #339933;">;</span>
        <span style="color: #666666; font-style: italic;">#有多少个目标地址，就创建多少个线程。其中grabdata是收集数据的sub。</span>
        <span style="color: #b1b100;">for</span> <span style="color: #b1b100;">my</span> <span style="color: #0000ff;">$snip</span> <span style="color: #009900;">&#40;</span><span style="color: #0000ff;">@snips</span><span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span>
            <span style="color: #000066;">push</span> <span style="color: #0000ff;">@threads</span><span style="color: #339933;">,</span>threads<span style="color: #339933;">-&gt;</span><span style="color: #006600;">create</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">\&amp;grabdata</span><span style="color: #339933;">,</span><span style="color: #0000ff;">$cnip</span><span style="color: #339933;">,</span><span style="color: #0000ff;">$snip</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
        <span style="color: #009900;">&#125;</span>
        <span style="color: #666666; font-style: italic;">#join所有线程，并写入到csv文件。</span>
        <span style="color: #b1b100;">for</span> <span style="color: #b1b100;">my</span> <span style="color: #0000ff;">$thread</span> <span style="color: #009900;">&#40;</span><span style="color: #0000ff;">@threads</span><span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span>
            <span style="color: #b1b100;">my</span> <span style="color: #0000ff;">$data</span> <span style="color: #339933;">=</span> <span style="color: #0000ff;">$thread</span><span style="color: #339933;">-&gt;</span><span style="color: #000066;">join</span><span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
            <span style="color: #b1b100;">my</span> <span style="color: #0000ff;">$statics</span> <span style="color: #339933;">=</span> <span style="color: #000066;">join</span><span style="color: #009900;">&#40;</span><span style="color: #ff0000;">&quot;,&quot;</span><span style="color: #339933;">,</span><span style="color: #0000ff;">@$data</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
            <span style="color: #000066;">print</span> <span style="color: #0000ff;">$OUT</span> <span style="color: #ff0000;">&quot;$statics<span style="color: #000099; font-weight: bold;">\n</span>&quot;</span><span style="color: #339933;">;</span>
        <span style="color: #009900;">&#125;</span>
        <span style="color: #666666; font-style: italic;">#关闭文件句柄，将buffer里的数据刷入文件</span>
        <span style="color: #000066;">close</span> <span style="color: #009900;">&#40;</span><span style="color: #0000ff;">$OUT</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
        <span style="color: #666666; font-style: italic;">#获取所有本地csv文件并上传。其中getcsv和upload是脚本中定义的sub。</span>
        <span style="color: #b1b100;">my</span> <span style="color: #0000ff;">@csvfiles</span> <span style="color: #339933;">=</span> getcsv<span style="color: #009900;">&#40;</span> <span style="color: #0000ff;">$reportdir</span> <span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
        <span style="color: #b1b100;">if</span> <span style="color: #009900;">&#40;</span> <span style="color: #0000ff;">$opts</span><span style="color: #009900;">&#123;</span>ftp<span style="color: #009900;">&#125;</span> <span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span>
            <span style="color: #b1b100;">for</span> <span style="color: #b1b100;">my</span> <span style="color: #0000ff;">$csvfile</span> <span style="color: #009900;">&#40;</span> <span style="color: #0000ff;">@csvfiles</span> <span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span>
                upload<span style="color: #009900;">&#40;</span><span style="color: #0000ff;">$opts</span><span style="color: #009900;">&#123;</span>ftp<span style="color: #009900;">&#125;</span><span style="color: #339933;">,</span><span style="color: #0000ff;">$opts</span><span style="color: #009900;">&#123;</span>user<span style="color: #009900;">&#125;</span><span style="color: #339933;">,</span><span style="color: #0000ff;">$opts</span><span style="color: #009900;">&#123;</span>pass<span style="color: #009900;">&#125;</span><span style="color: #339933;">,</span><span style="color: #ff0000;">&quot;$csvfile&quot;</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
            <span style="color: #009900;">&#125;</span>
        <span style="color: #009900;">&#125;</span></pre></td></tr></table><p class="theCode" style="display:none;">    my @threads;
        my @snips = split /,/,$opts{dest};
        #有多少个目标地址，就创建多少个线程。其中grabdata是收集数据的sub。
        for my $snip (@snips) {
            push @threads,threads-&gt;create(\&amp;grabdata,$cnip,$snip);
        }
        #join所有线程，并写入到csv文件。
        for my $thread (@threads) {
            my $data = $thread-&gt;join();
            my $statics = join(&quot;,&quot;,@$data);
            print $OUT &quot;$statics\n&quot;;
        }
        #关闭文件句柄，将buffer里的数据刷入文件
        close ($OUT);
        #获取所有本地csv文件并上传。其中getcsv和upload是脚本中定义的sub。
        my @csvfiles = getcsv( $reportdir );
        if ( $opts{ftp} ) {
            for my $csvfile ( @csvfiles ) {
                upload($opts{ftp},$opts{user},$opts{pass},&quot;$csvfile&quot;);
            }
        }</p></div>
    ";}
categories:
  - 代码卷轴
tags:
  - perl
  - 多线程

---
前些日子在写一些 Perl 脚本的时候为了追求处理速度或者时间上的平行，频繁地使用到了 Perl 的多线程功能。在类 UNIX 的 OS 上，Perl 的多线程还算可靠的，虽然 perldoc 也并不推荐使用多线程，但是应用场景实在太多，几乎不太可能完全不用。

Perl 内置有一个多线程模块 <a href="http://perldoc.perl.org/threads.html" title="threads perl doc" target="_blank">Thread</a> ，提供了常规意义上的multithreads功能，可以满足我们的一般需求。下面以一个简单的收集Ping数据的脚本为例。
  
<!--more-->

<img src="https://www.digglife.net/wp-content/uploads/2014/03/multithread.jpg" alt="Perl多线程处理" width="600" height="330" class="alignnone size-full wp-image-3864" />

要实现的目的是，收集本机 ping 多个远程 IP 产生的数据，写入到 csv 文件，然后上传的远程FTP上做后期处理。有关多线程的代码如下。其中 `$cnip` 是通过另一个 sub获取到的本机地址，`@snip`是配置文件中读取（或者参数中）读取到的目标地址。

<pre lang='perl'  line='1'>my @threads;
    my @snips = split /,/,$opts{dest};
    #有多少个目标地址，就创建多少个线程。其中grabdata是收集数据的sub。
    for my $snip (@snips) {
        push @threads,threads->create(\&grabdata,$cnip,$snip);
    }
    #join所有线程，并写入到csv文件。
    for my $thread (@threads) {
        my $data = $thread->join();
        my $statics = join(",",@$data);
        print $OUT "$statics\n";
    }
    #关闭文件句柄，将buffer里的数据刷入文件
    close ($OUT);
    #获取所有本地csv文件并上传。其中getcsv和upload是脚本中定义的sub。
    my @csvfiles = getcsv( $reportdir );
    if ( $opts{ftp} ) {
        for my $csvfile ( @csvfiles ) {
            upload($opts{ftp},$opts{user},$opts{pass},"$csvfile");
        }
    }
</pre>

基本原理很简单，为每一个 grabdata 操作都创建一个thread，遍历所有 thread，join到主线程并获取返回值，写入到本地文件，然后上传。

其中有几个需要注意的地方：

  1. thread的默认返回值是scalar
如果sub的返回值是array，可以返回array的ref（如上例），或者直接在 create 时传入hash ref指定： ``前些日子在写一些 Perl 脚本的时候为了追求处理速度或者时间上的平行，频繁地使用到了 Perl 的多线程功能。在类 UNIX 的 OS 上，Perl 的多线程还算可靠的，虽然 perldoc 也并不推荐使用多线程，但是应用场景实在太多，几乎不太可能完全不用。

Perl 内置有一个多线程模块 <a href="http://perldoc.perl.org/threads.html" title="threads perl doc" target="_blank">Thread</a> ，提供了常规意义上的multithreads功能，可以满足我们的一般需求。下面以一个简单的收集Ping数据的脚本为例。
  
<!--more-->

<img src="https://www.digglife.net/wp-content/uploads/2014/03/multithread.jpg" alt="Perl多线程处理" width="600" height="330" class="alignnone size-full wp-image-3864" />

要实现的目的是，收集本机 ping 多个远程 IP 产生的数据，写入到 csv 文件，然后上传的远程FTP上做后期处理。有关多线程的代码如下。其中 `$cnip` 是通过另一个 sub获取到的本机地址，`@snip`是配置文件中读取（或者参数中）读取到的目标地址。

<pre lang='perl'  line='1'>my @threads;
    my @snips = split /,/,$opts{dest};
    #有多少个目标地址，就创建多少个线程。其中grabdata是收集数据的sub。
    for my $snip (@snips) {
        push @threads,threads->create(\&grabdata,$cnip,$snip);
    }
    #join所有线程，并写入到csv文件。
    for my $thread (@threads) {
        my $data = $thread->join();
        my $statics = join(",",@$data);
        print $OUT "$statics\n";
    }
    #关闭文件句柄，将buffer里的数据刷入文件
    close ($OUT);
    #获取所有本地csv文件并上传。其中getcsv和upload是脚本中定义的sub。
    my @csvfiles = getcsv( $reportdir );
    if ( $opts{ftp} ) {
        for my $csvfile ( @csvfiles ) {
            upload($opts{ftp},$opts{user},$opts{pass},"$csvfile");
        }
    }
</pre>

基本原理很简单，为每一个 grabdata 操作都创建一个thread，遍历所有 thread，join到主线程并获取返回值，写入到本地文件，然后上传。

其中有几个需要注意的地方：

  1. thread的默认返回值是scalar
如果sub的返回值是array，可以返回array的ref（如上例），或者直接在 create 时传入hash ref指定：`` 。

  2. `join` VS `detach`
上例用到join只是因为我需要每个 grabdata sub 的返回值，如果创建Thread只是为了达到并行处理的目的，线程的返回值不重要，可以创建后  ```前些日子在写一些 Perl 脚本的时候为了追求处理速度或者时间上的平行，频繁地使用到了 Perl 的多线程功能。在类 UNIX 的 OS 上，Perl 的多线程还算可靠的，虽然 perldoc 也并不推荐使用多线程，但是应用场景实在太多，几乎不太可能完全不用。

Perl 内置有一个多线程模块 <a href="http://perldoc.perl.org/threads.html" title="threads perl doc" target="_blank">Thread</a> ，提供了常规意义上的multithreads功能，可以满足我们的一般需求。下面以一个简单的收集Ping数据的脚本为例。
  
<!--more-->

<img src="https://www.digglife.net/wp-content/uploads/2014/03/multithread.jpg" alt="Perl多线程处理" width="600" height="330" class="alignnone size-full wp-image-3864" />

要实现的目的是，收集本机 ping 多个远程 IP 产生的数据，写入到 csv 文件，然后上传的远程FTP上做后期处理。有关多线程的代码如下。其中 `$cnip` 是通过另一个 sub获取到的本机地址，`@snip`是配置文件中读取（或者参数中）读取到的目标地址。

<pre lang='perl'  line='1'>my @threads;
    my @snips = split /,/,$opts{dest};
    #有多少个目标地址，就创建多少个线程。其中grabdata是收集数据的sub。
    for my $snip (@snips) {
        push @threads,threads->create(\&grabdata,$cnip,$snip);
    }
    #join所有线程，并写入到csv文件。
    for my $thread (@threads) {
        my $data = $thread->join();
        my $statics = join(",",@$data);
        print $OUT "$statics\n";
    }
    #关闭文件句柄，将buffer里的数据刷入文件
    close ($OUT);
    #获取所有本地csv文件并上传。其中getcsv和upload是脚本中定义的sub。
    my @csvfiles = getcsv( $reportdir );
    if ( $opts{ftp} ) {
        for my $csvfile ( @csvfiles ) {
            upload($opts{ftp},$opts{user},$opts{pass},"$csvfile");
        }
    }
</pre>

基本原理很简单，为每一个 grabdata 操作都创建一个thread，遍历所有 thread，join到主线程并获取返回值，写入到本地文件，然后上传。

其中有几个需要注意的地方：

  1. thread的默认返回值是scalar
如果sub的返回值是array，可以返回array的ref（如上例），或者直接在 create 时传入hash ref指定： ``前些日子在写一些 Perl 脚本的时候为了追求处理速度或者时间上的平行，频繁地使用到了 Perl 的多线程功能。在类 UNIX 的 OS 上，Perl 的多线程还算可靠的，虽然 perldoc 也并不推荐使用多线程，但是应用场景实在太多，几乎不太可能完全不用。

Perl 内置有一个多线程模块 <a href="http://perldoc.perl.org/threads.html" title="threads perl doc" target="_blank">Thread</a> ，提供了常规意义上的multithreads功能，可以满足我们的一般需求。下面以一个简单的收集Ping数据的脚本为例。
  
<!--more-->

<img src="https://www.digglife.net/wp-content/uploads/2014/03/multithread.jpg" alt="Perl多线程处理" width="600" height="330" class="alignnone size-full wp-image-3864" />

要实现的目的是，收集本机 ping 多个远程 IP 产生的数据，写入到 csv 文件，然后上传的远程FTP上做后期处理。有关多线程的代码如下。其中 `$cnip` 是通过另一个 sub获取到的本机地址，`@snip`是配置文件中读取（或者参数中）读取到的目标地址。

<pre lang='perl'  line='1'>my @threads;
    my @snips = split /,/,$opts{dest};
    #有多少个目标地址，就创建多少个线程。其中grabdata是收集数据的sub。
    for my $snip (@snips) {
        push @threads,threads->create(\&grabdata,$cnip,$snip);
    }
    #join所有线程，并写入到csv文件。
    for my $thread (@threads) {
        my $data = $thread->join();
        my $statics = join(",",@$data);
        print $OUT "$statics\n";
    }
    #关闭文件句柄，将buffer里的数据刷入文件
    close ($OUT);
    #获取所有本地csv文件并上传。其中getcsv和upload是脚本中定义的sub。
    my @csvfiles = getcsv( $reportdir );
    if ( $opts{ftp} ) {
        for my $csvfile ( @csvfiles ) {
            upload($opts{ftp},$opts{user},$opts{pass},"$csvfile");
        }
    }
</pre>

基本原理很简单，为每一个 grabdata 操作都创建一个thread，遍历所有 thread，join到主线程并获取返回值，写入到本地文件，然后上传。

其中有几个需要注意的地方：

  1. thread的默认返回值是scalar
如果sub的返回值是array，可以返回array的ref（如上例），或者直接在 create 时传入hash ref指定：`` 。

  2. `join` VS `detach`
上例用到join只是因为我需要每个 grabdata sub 的返回值，如果创建Thread只是为了达到并行处理的目的，线程的返回值不重要，可以创建后``` 。

  3. 危险的IO Buffer
这个虽然和多线程没有直接关系，但是令我印象深刻，所以还是记录一下。因为以前用到 file handler 从来不会手动 close，在这里就悲剧了。Perl在处理 file handler 的时候为了减少文件IO以提高性能，有一个 buffer 机制。比如上例在for循环中写入`$OUT`，perl并不会在每次循环都写入文件，而是暂时保存在 buffer 里。如果不手动 close 的话，最终上传的将是一个空文件。Perl 诡异的 Buffer 迷惑了很多人，于是就有了<a href="http://perl.plover.com/FAQs/Buffering.html" title="Suffering from Buffering?" target="_blank">这坨长篇大论</a>。 </ol> 

内置的thread模块可以满足一般多线程的需求，但是没有解决一些我们经常会碰到的问题：

  1. 无法固定线程个数，排队处理
比如，我需要发送1000个http request，显然同时发送害人害己。比较自然的想法是，创建比如20个线程，某一个线程完毕后，程序自动补上一个，保证同时只有20个线程。事实上，thread 结合 thread::queue 模块可以实现，但是十分费解，手动要做的事情太多，而且容易侧漏。

  2. 线程之间变量共享比较困难
上例中，各个线程的变量是独立的。但是很多情况下我们需要所有线程共享一个数据结构，比如 push 数据到同一个array，thread 模块无法解决。thread::shared 模块号称能够共享变量，但是对于array和hash还是无能为力。

Perl的built-in功能虽然有限，但是大CPAN是万能的，有一个第三方模块可以很好的解决这个问题。下回再细说。
