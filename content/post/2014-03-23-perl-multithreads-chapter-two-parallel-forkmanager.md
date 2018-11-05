---
title: Perl的多线程应用之二：Parallel::ForkManager
author: 摩摩诘
type: post
date: 2014-03-22T16:23:58+00:00
excerpt: 内置的 Thread 模块无法解决线程排队、变量共享的问题，但是在使用多线程的过程中，这两个又是比较常见的需求。线程数无法控制，处理速度和内存消耗两者无法平衡；变量无法共享，无法让线程向同一个数据结构传递返回值。但是CPAN 上有一个备受匿名和尚们推崇的模块能够很好地解决这些问题，这个模块就是传说中的 Parallel::ForkManager 。
url: /articles/perl-multithreads-chapter-two-parallel-forkmanager.html
index_image:
  - https://www.digglife.net/wp-content/uploads/2014/03/perl-threads.jpg
duoshuo_thread_id:
  - 1154125469839262180
views:
  - 1724
wp-syntax-cache-content:
  - |
    a:3:{i:1;s:2473:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="line_numbers"><pre>1
    2
    3
    4
    </pre></td><td class="code"><pre class="perl" style="font-family:monospace;"><span style="display:block;background-color: #ffc;">  <span style="color: #b1b100;">while</span> <span style="color: #009900;">&#40;</span><span style="color: #0000ff;">$s</span><span style="color: #339933;">-&gt;</span><span style="color: #009900;">&#123;</span>max_proc<span style="color: #009900;">&#125;</span> <span style="color: #339933;">&amp;&amp;</span> <span style="color: #009900;">&#40;</span> <span style="color: #000066;">keys</span> <span style="color: #339933;">%</span><span style="color: #009900;">&#123;</span> <span style="color: #0000ff;">$s</span><span style="color: #339933;">-&gt;</span><span style="color: #009900;">&#123;</span>processes<span style="color: #009900;">&#125;</span> <span style="color: #009900;">&#125;</span> <span style="color: #009900;">&#41;</span> <span style="color: #339933;">&gt;=</span> <span style="color: #0000ff;">$s</span><span style="color: #339933;">-&gt;</span><span style="color: #009900;">&#123;</span>max_proc<span style="color: #009900;">&#125;</span><span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span></span>    <span style="color: #0000ff;">$s</span><span style="color: #339933;">-&gt;</span><span style="color: #006600;">on_wait</span><span style="color: #339933;">;</span>
        <span style="color: #0000ff;">$s</span><span style="color: #339933;">-&gt;</span><span style="color: #006600;">wait_one_child</span><span style="color: #009900;">&#40;</span><span style="color: #000066;">defined</span> <span style="color: #0000ff;">$s</span><span style="color: #339933;">-&gt;</span><span style="color: #009900;">&#123;</span>on_wait_period<span style="color: #009900;">&#125;</span> <span style="color: #339933;">?</span> <span style="color: #0000ff;">&amp;WNOHANG</span> <span style="color: #339933;">:</span> <span style="color: #000066;">undef</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
      <span style="color: #009900;">&#125;</span><span style="color: #339933;">;</span></pre></td></tr></table><p class="theCode" style="display:none;">  while ($s-&gt;{max_proc} &amp;&amp; ( keys %{ $s-&gt;{processes} } ) &gt;= $s-&gt;{max_proc}) {
        $s-&gt;on_wait;
        $s-&gt;wait_one_child(defined $s-&gt;{on_wait_period} ? &amp;WNOHANG : undef);
      };</p></div>
    ";i:2;s:4465:"
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
    </pre></td><td class="code"><pre class="perl" style="font-family:monospace;">  <span style="color: #b1b100;">if</span> <span style="color: #009900;">&#40;</span> <span style="color: #0000ff;">$s</span><span style="color: #339933;">-&gt;</span><span style="color: #009900;">&#123;</span>in_child<span style="color: #009900;">&#125;</span> <span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span>
        <span style="color: #b1b100;">if</span> <span style="color: #009900;">&#40;</span><span style="color: #000066;">defined</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">$r</span><span style="color: #009900;">&#41;</span><span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span>  <span style="color: #666666; font-style: italic;"># store the child's data structure</span>
          <span style="color: #b1b100;">my</span> <span style="color: #0000ff;">$storable_tempfile</span> <span style="color: #339933;">=</span> File<span style="color: #339933;">::</span><span style="color: #006600;">Spec</span><span style="color: #339933;">-&gt;</span><span style="color: #006600;">catfile</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">$s</span><span style="color: #339933;">-&gt;</span><span style="color: #009900;">&#123;</span>tempdir<span style="color: #009900;">&#125;</span><span style="color: #339933;">,</span> <span style="color: #ff0000;">'Parallel-ForkManager-'</span> <span style="color: #339933;">.</span> <span style="color: #0000ff;">$s</span><span style="color: #339933;">-&gt;</span><span style="color: #009900;">&#123;</span>parent_pid<span style="color: #009900;">&#125;</span> <span style="color: #339933;">.</span> <span style="color: #ff0000;">'-'</span> <span style="color: #339933;">.</span> <span style="color: #0000ff;">$$</span> <span style="color: #339933;">.</span> <span style="color: #ff0000;">'.txt'</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
          <span style="color: #b1b100;">my</span> <span style="color: #0000ff;">$stored</span> <span style="color: #339933;">=</span> <span style="color: #000066;">eval</span> <span style="color: #009900;">&#123;</span> <span style="color: #000066;">return</span> <span style="color: #0000ff;">&amp;store</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">$r</span><span style="color: #339933;">,</span> <span style="color: #0000ff;">$storable_tempfile</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span> <span style="color: #009900;">&#125;</span><span style="color: #339933;">;</span>
    &nbsp;
          <span style="color: #666666; font-style: italic;"># handle Storables errors, IE logcarp or carp returning undef, or die (via logcroak or croak)</span>
          <span style="color: #b1b100;">if</span> <span style="color: #009900;">&#40;</span><span style="color: #b1b100;">not</span> <span style="color: #0000ff;">$stored</span> <span style="color: #b1b100;">or</span> <span style="color: #0000ff;">$@</span><span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span>
            <span style="color: #000066;">warn</span><span style="color: #009900;">&#40;</span><span style="color: #000066;">qq</span><span style="color: #339933;">|</span>The storable module was unable to store the child<span style="color: #ff0000;">'s data structure to the temp file &quot;$storable_tempfile&quot;:  | . join('</span><span style="color: #339933;">,</span> <span style="color: #ff0000;">', $@));
          }
        }
        CORE::exit($x || 0);
      }</span></pre></td></tr></table><p class="theCode" style="display:none;">  if ( $s-&gt;{in_child} ) {
        if (defined($r)) {  # store the child's data structure
          my $storable_tempfile = File::Spec-&gt;catfile($s-&gt;{tempdir}, 'Parallel-ForkManager-' . $s-&gt;{parent_pid} . '-' . $$ . '.txt');
          my $stored = eval { return &amp;store($r, $storable_tempfile); };
    
          # handle Storables errors, IE logcarp or carp returning undef, or die (via logcroak or croak)
          if (not $stored or $@) {
            warn(qq|The storable module was unable to store the child's data structure to the temp file &quot;$storable_tempfile&quot;:  | . join(', ', $@));
          }
        }
        CORE::exit($x || 0);
      }</p></div>
    ";i:3;s:7560:"
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
    32
    33
    34
    35
    36
    37
    38
    39
    </pre></td><td class="code"><pre class="perl" style="font-family:monospace;"><span style="color: #000000; font-weight: bold;">use</span> strict<span style="color: #339933;">;</span>
    <span style="color: #000000; font-weight: bold;">use</span> warnings<span style="color: #339933;">;</span>
    <span style="color: #000000; font-weight: bold;">use</span> Parallel<span style="color: #339933;">::</span><span style="color: #006600;">ForkManager</span><span style="color: #339933;">;</span>
    &nbsp;
    &nbsp;
    <span style="color: #666666; font-style: italic;"># 指定进程峰值为100</span>
    <span style="display:block;background-color: #ffc;"><span style="color: #b1b100;">my</span> <span style="color: #0000ff;">$pm</span> <span style="color: #339933;">=</span> Parallel<span style="color: #339933;">::</span><span style="color: #006600;">ForkManager</span><span style="color: #339933;">-&gt;</span><span style="color: #000000; font-weight: bold;">new</span><span style="color: #009900;">&#40;</span><span style="color: #cc66cc;">100</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span></span><span style="color: #666666; font-style: italic;"># 所有子进程返回的数据结构都会传回到这个hash里</span>
    <span style="color: #b1b100;">my</span> <span style="color: #0000ff;">%persons</span><span style="color: #339933;">;</span>
    &nbsp;
    <span style="color: #666666; font-style: italic;"># 进程结束时运行的callback，将子进程返回的数据结构传入%persons，</span>
    <span style="color: #666666; font-style: italic;"># 这是“共享数据结构”的关键</span>
    <span style="display:block;background-color: #ffc;"><span style="color: #0000ff;">$pm</span> <span style="color: #339933;">-&gt;</span> <span style="color: #006600;">run_on_finish</span><span style="color: #009900;">&#40;</span> <span style="color: #000000; font-weight: bold;">sub</span> <span style="color: #009900;">&#123;</span></span><span style="display:block;background-color: #ffc;">        <span style="color: #b1b100;">my</span> <span style="color: #0000ff;">$person_info</span> <span style="color: #339933;">=</span> <span style="color: #000066;">pop</span> <span style="color: #0000ff;">@_</span><span style="color: #339933;">;</span></span><span style="display:block;background-color: #ffc;">        <span style="color: #b1b100;">while</span> <span style="color: #009900;">&#40;</span> <span style="color: #b1b100;">my</span> <span style="color: #009900;">&#40;</span><span style="color: #0000ff;">$key</span><span style="color: #339933;">,</span><span style="color: #0000ff;">$value</span><span style="color: #009900;">&#41;</span> <span style="color: #339933;">=</span> <span style="color: #000066;">each</span> <span style="color: #0000ff;">%$person_info</span> <span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span></span><span style="display:block;background-color: #ffc;">            <span style="color: #0000ff;">$persons</span><span style="color: #009900;">&#123;</span><span style="color: #0000ff;">$key</span><span style="color: #009900;">&#125;</span> <span style="color: #339933;">=</span> <span style="color: #0000ff;">$value</span><span style="color: #339933;">;</span></span><span style="display:block;background-color: #ffc;">        <span style="color: #009900;">&#125;</span></span><span style="display:block;background-color: #ffc;">    <span style="color: #009900;">&#125;</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span></span>&nbsp;
    <span style="color: #b1b100;">for</span> <span style="color: #b1b100;">my</span> <span style="color: #0000ff;">$email</span> <span style="color: #009900;">&#40;</span> <span style="color: #0000ff;">@emails</span> <span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span>
        <span style="color: #666666; font-style: italic;"># 创建进程</span>
        <span style="color: #0000ff;">$pm</span><span style="color: #339933;">-&gt;</span><span style="color: #006600;">start</span> <span style="color: #b1b100;">and</span> <span style="color: #b1b100;">next</span><span style="color: #339933;">;</span>
        <span style="color: #666666; font-style: italic;"># 实际需要运行的代码</span>
        <span style="color: #b1b100;">my</span> <span style="color: #0000ff;">$data</span> <span style="color: #339933;">=</span> get_person_info<span style="color: #009900;">&#40;</span><span style="color: #0000ff;">$email</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    &nbsp;
        <span style="color: #666666; font-style: italic;"># 结束进程并返回$data。</span>
        <span style="color: #666666; font-style: italic;"># $data是一个array ref，其中有进程id，进程退出码等信息，</span>
        <span style="color: #666666; font-style: italic;"># 其中最后一个item是子进程返回的数据结构。</span>
        <span style="color: #0000ff;">$pm</span><span style="color: #339933;">-&gt;</span><span style="color: #006600;">finish</span><span style="color: #009900;">&#40;</span><span style="color: #cc66cc;">0</span><span style="color: #339933;">,</span> <span style="color: #0000ff;">$data</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    <span style="color: #009900;">&#125;</span>
    &nbsp;
    <span style="color: #0000ff;">$pm</span><span style="color: #339933;">-&gt;</span><span style="color: #006600;">wait_all_children</span><span style="color: #339933;">;</span>
    &nbsp;
    <span style="color: #666666; font-style: italic;"># 伪sub</span>
    <span style="color: #000000; font-weight: bold;">sub</span> get_person_info <span style="color: #009900;">&#123;</span>
        <span style="color: #b1b100;">my</span> <span style="color: #0000ff;">$email</span> <span style="color: #339933;">=</span> <span style="color: #000066;">shift</span> <span style="color: #0000ff;">@_</span><span style="color: #339933;">;</span>
        <span style="color: #666666; font-style: italic;"># bla bla bla</span>
        <span style="color: #000066;">return</span> <span style="color: #0000ff;">\%person_info</span><span style="color: #339933;">;</span>
    <span style="color: #009900;">&#125;</span></pre></td></tr></table><p class="theCode" style="display:none;">use strict;
    use warnings;
    use Parallel::ForkManager;
    
    
    # 指定进程峰值为100
    my $pm = Parallel::ForkManager-&gt;new(100);
    # 所有子进程返回的数据结构都会传回到这个hash里
    my %persons;
    
    # 进程结束时运行的callback，将子进程返回的数据结构传入%persons，
    # 这是“共享数据结构”的关键
    $pm -&gt; run_on_finish( sub {
            my $person_info = pop @_;
            while ( my ($key,$value) = each %$person_info ) {
                $persons{$key} = $value;
            }
        });
    
    for my $email ( @emails ) {
        # 创建进程
        $pm-&gt;start and next;
        # 实际需要运行的代码
        my $data = get_person_info($email);
        
        # 结束进程并返回$data。
        # $data是一个array ref，其中有进程id，进程退出码等信息，
        # 其中最后一个item是子进程返回的数据结构。
        $pm-&gt;finish(0, $data);
    }
    
    $pm-&gt;wait_all_children;
    
    # 伪sub
    sub get_person_info {
        my $email = shift @_;
        # bla bla bla
        return \%person_info;
    }</p></div>
    ";}
categories:
  - 代码卷轴
tags:
  - forkmanager
  - perl
  - 多线程

---
上一篇日志说过了，内置的 Thread 模块无法解决线程排队、变量共享的问题，但是在使用多线程的过程中，这两个又是比较常见的需求。线程数无法控制，处理速度和内存消耗两者无法平衡；变量无法共享，无法让线程向同一个数据结构传递返回值。但是 Perl 有庞大的第三方库，CPAN 上有一个备受匿名和尚们推崇的模块能够很好地解决这些问题，这个模块就是传说中的 <a href="http://search.cpan.org/~szabgab/Parallel-ForkManager-1.06/lib/Parallel/ForkManager.pm" title="多进程处理模块 Parallel::ForkManager" target="_blank">Parallel::ForkManager</a> 。严格意义上说这个模块是通过 Fork 进程而不是创建线程来实现并行处理的，不过在实际应用过程中，这两者其实没什么区别。
  
<!--more-->

<img src="https://www.digglife.net/wp-content/uploads/2014/03/multithread2.jpg" alt="Perl多线程" width="600" height="350" class="alignnone size-full wp-image-3866" />
  
Parallel::ForkManager 代码也只有寥寥的200多行，内容并不艰深。

对于线程排队，ForkManager 只是在 fork 进程的方法里添加了一个判断，如果当前子进程数量>=事先定义的数量，就调用等待方法。

<pre lang='perl' line='1' highlight='1'>while ($s->{max_proc} && ( keys %{ $s->{processes} } ) >= $s->{max_proc}) {
    $s->on_wait;
    $s->wait_one_child(defined $s->{on_wait_period} ? &WNOHANG : undef);
  };
</pre>

对于变量共享， 它利用 <a href="http://perldoc.perl.org/Storable.html" title="Perl的Storable模块" target="_blank">Storable 模块</a> 将子线程的数据结构序列化之后转换成文本，然后主线程再反其道行之将文本读取到内存，这样就绕开了复杂的 <a href="http://perldoc.perl.org/functions/lock.html" title="Perl lock function" target="_blank">variable lock</a>，当然，因为涉及到磁盘IO，性能也会打折扣。这个实现方式也有很大的局限，严格说来并不算是所谓的变量共享，我在最后会讨论这个问题。

<pre lang='perl' line='1'>if ( $s->{in_child} ) {
    if (defined($r)) {  # store the child's data structure
      my $storable_tempfile = File::Spec->catfile($s->{tempdir}, 'Parallel-ForkManager-' . $s->{parent_pid} . '-' . $$ . '.txt');
      my $stored = eval { return &store($r, $storable_tempfile); };

      # handle Storables errors, IE logcarp or carp returning undef, or die (via logcroak or croak)
      if (not $stored or $@) {
        warn(qq|The storable module was unable to store the child's data structure to the temp file "$storable_tempfile":  | . join(', ', $@));
      }
    }
    CORE::exit($x || 0);
  }
</pre>

下面是一个简单的示例：

<pre lang='perl' line='1' highlight='7,13,14,15,16,17,18'>use strict;
use warnings;
use Parallel::ForkManager;


# 指定进程峰值为100
my $pm = Parallel::ForkManager->new(100);
# 所有子进程返回的数据结构都会传回到这个hash里
my %persons;

# 进程结束时运行的callback，将子进程返回的数据结构传入%persons，
# 这是“共享数据结构”的关键
$pm -> run_on_finish( sub {
        my $person_info = pop @_;
        while ( my ($key,$value) = each %$person_info ) {
            $persons{$key} = $value;
        }
    });

for my $email ( @emails ) {
    # 创建进程
    $pm->start and next;
    # 实际需要运行的代码
    my $data = get_person_info($email);
    
    # 结束进程并返回$data。
    # $data是一个array ref，其中有进程id，进程退出码等信息，
    # 其中最后一个item是子进程返回的数据结构。
    $pm->finish(0, $data);
}

$pm->wait_all_children;

# 伪sub
sub get_person_info {
    my $email = shift @_;
    # bla bla bla
    return \%person_info;
}
</pre>

上面代码的关键在于在创建PM对象的时候设定进程最大值，以及设定 `run_on_finish` 的 callback 。之前提到利用 `run_on_finish` 有一定局限，如果我希望在子线程的代码中加入条件判断，将不同类别的数据输出到两个不同的共享hash就不怎么好处理了。此外，如果子进程需要实时从共享hash 中读取数据，ForkManager 是无法做到的。如果不想自己写代码，可以利用另外一个CPAN模块，下一篇再说。
