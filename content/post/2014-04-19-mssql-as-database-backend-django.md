---
title: Linux上使用MSSQL Server作为Django的Database Backend
author: 摩摩诘
type: post
date: 2014-04-18T16:54:42+00:00
excerpt: Django只内置了几个 Database Backend，默认并不支持MSSQL。官方手册中提供的第三方 MSSQL Backend 因为依赖的问题只支持 Windows 平台，在 Linux Server 上不可用。庆幸的是微软“大发慈悲”在2012年给 Redhat 提供了官方ODBC驱动（以前得用第三方的FreeTDS），而 Django 的第三方库中有比较完善的 ODBC 支持，所以我们可以迂回实现。
url: /articles/mssql-as-database-backend-django.html
duoshuo_thread_id:
  - 1154125469839262181
index_image:
  - https://www.digglife.net/wp-content/uploads/2014/03/django-mssql.png
views:
  - 866
wp-syntax-cache-content:
  - |
    a:3:{i:1;s:976:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="line_numbers"><pre>1
    2
    3
    </pre></td><td class="code"><pre class="python" style="font-family:monospace;"><span style="color: #ff7700;font-weight:bold;">import</span> pyodbc
    connection <span style="color: #66cc66;">=</span> pyodbc.<span style="color: black;">connect</span><span style="color: black;">&#40;</span><span style="color: #483d8b;">'DRIVER={SQL Server Native Client 10.0};SERVER=127.0.0.1;DATABASE=test;UID=user;PWD=password'</span><span style="color: black;">&#41;</span>
    cousor <span style="color: #66cc66;">=</span> connection.<span style="color: black;">cursor</span><span style="color: black;">&#40;</span><span style="color: black;">&#41;</span></pre></td></tr></table><p class="theCode" style="display:none;">import pyodbc
    connection = pyodbc.connect('DRIVER={SQL Server Native Client 10.0};SERVER=127.0.0.1;DATABASE=test;UID=user;PWD=password')
    cousor = connection.cursor()</p></div>
    ";i:2;s:1622:"
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
    </pre></td><td class="code"><pre class="python" style="font-family:monospace;"><span style="color: #483d8b;">'test'</span>:<span style="color: black;">&#123;</span>
        <span style="color: #483d8b;">'ENGINE'</span>:<span style="color: #483d8b;">'django_pyodbc'</span><span style="color: #66cc66;">,</span>
        <span style="color: #483d8b;">'NAME'</span>:<span style="color: #483d8b;">'test'</span><span style="color: #66cc66;">,</span>
        <span style="color: #483d8b;">'HOST'</span>:<span style="color: #483d8b;">'127.0.0.1'</span><span style="color: #66cc66;">,</span>
        <span style="color: #483d8b;">'USER'</span>:<span style="color: #483d8b;">'test'</span><span style="color: #66cc66;">,</span>
        <span style="color: #483d8b;">'PASSWORD'</span>:<span style="color: #483d8b;">'password'</span><span style="color: #66cc66;">,</span>
        <span style="color: #483d8b;">'OPTIONS'</span>: <span style="color: black;">&#123;</span>
            <span style="color: #483d8b;">'driver'</span>: <span style="color: #483d8b;">'SQL Server Native Client 11.0'</span><span style="color: #66cc66;">,</span>
        <span style="color: black;">&#125;</span><span style="color: #66cc66;">,</span>
    <span style="color: black;">&#125;</span></pre></td></tr></table><p class="theCode" style="display:none;">'test':{
        'ENGINE':'django_pyodbc',
        'NAME':'test',
        'HOST':'127.0.0.1',
        'USER':'test',
        'PASSWORD':'password',
        'OPTIONS': {
            'driver': 'SQL Server Native Client 11.0',
        },
    }</p></div>
    ";i:3;s:1193:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="line_numbers"><pre>1
    2
    3
    4
    </pre></td><td class="code"><pre class="python" style="font-family:monospace;"><span style="color: #ff7700;font-weight:bold;">from</span> django.<span style="color: black;">db</span> <span style="color: #ff7700;font-weight:bold;">import</span> connections
    cur <span style="color: #66cc66;">=</span> connections<span style="color: black;">&#91;</span><span style="color: #483d8b;">'test'</span><span style="color: black;">&#93;</span>.<span style="color: black;">cursor</span><span style="color: black;">&#40;</span><span style="color: black;">&#41;</span>
    cur.<span style="color: black;">execute</span><span style="color: black;">&#40;</span><span style="color: #483d8b;">&quot;SELECT * FROM testtable&quot;</span><span style="color: black;">&#41;</span>
    cur.<span style="color: black;">fetchone</span><span style="color: black;">&#40;</span><span style="color: black;">&#41;</span></pre></td></tr></table><p class="theCode" style="display:none;">from django.db import connections
    cur = connections['test'].cursor()
    cur.execute(&quot;SELECT * FROM testtable&quot;)
    cur.fetchone()</p></div>
    ";}
categories:
  - 代码卷轴
tags:
  - django
  - mssql
  - python
  - 微软
format: aside

---
Django只内置了几个 Database Backend，默认并不支持 `Microsoft SQL Server`（ 以下用 MSSQL 代替 ）。官方手册中提供的第三方 MSSQL Backend 因为依赖的问题只支持 Windows 平台，在 <a href="https://www.digglife.net/articles/category/about_ubuntu" title="Linux相关文章" target="_blank">Linux</a> Server 上不可用。可能很多人会问，谁会在 Linux 上用邪恶的 MSSQL 当 Django 的数据库后台，其实在企业中很多事情身不由己，各种奇葩的需求都会有，这种算是比较小儿科的了。庆幸的是微软“大发慈悲”在2012年给 Redhat 提供了官方ODBC驱动（以前得用第三方的FreeTDS），而 Django 的第三方库中有比较完善的 ODBC 支持，所以我们可以迂回实现。

<!--more-->

实现模式：`MSSQL Server -> MSSQL Server ODBC Driver -> pyodbc -> django-pyodbc -> django frontend` 。

<img src="https://www.digglife.net/wp-content/uploads/2014/04/mssql-django.jpg" alt="Linux上使用MSSQL Server作为Django的Database Backend" width="484" height="187" class="alignnone size-full wp-image-3921" />

### 安装MSSQL Server ODBC Driver 1.0

到微软的 Download Center<a href="http://www.microsoft.com/en-us/download/details.aspx?id=28160" title="Microsoft® SQL Server® ODBC Driver 1.0 for Linux " target="_blank">下载 MSSQL Server ODBC Driver </a>，注意目前只支持64位的 RHEL 5/6 ，理论上 CentOS 也是支持的。压缩包里的 README 有详细的安装说明，也有比较完善的Shell安装脚本，我安装的时候并没有碰到什么异常。基本步骤：

  1. 如果Server上已经安装有 `unixODBC DriverManager`，先卸载。
  2. 使用压缩包中的 build_dm.sh 编译安装 `unixODBC DriverManager`。
这样做的好处是可以保证 configure 的各项参数符合要求，比如MSSQL的默认unicode字符集是UTF-16，所以 configure 参数里需要有`--with-iconv-ucode-enc=UTF16LE`。

  3. 确定 `unixODBC` 正确安装之后，就可以运行 `./install.sh install` 来安装 MSSQL Server ODBC Driver了。

### 安装pyodbc和django-pyodbc

`sudo pip install pyodbc django_pyodbc`即可。其实安装完pyodbc我们就可以在python的shell下测试了驱动是否安装成功。

<pre lang='python' line='1'>import pyodbc
connection = pyodbc.connect('DRIVER={SQL Server Native Client 10.0};SERVER=127.0.0.1;DATABASE=test;UID=user;PWD=password')
cousor = connection.cursor()
</pre>

如果提示无法import，多半是权限问题。

### 配置django settings

在 project 的 `settings.py` 中添加新的数据库设定，示例一枚：

<pre lang='python' line='1'>'test':{
    'ENGINE':'django_pyodbc',
    'NAME':'test',
    'HOST':'127.0.0.1',
    'USER':'test',
    'PASSWORD':'password',
    'OPTIONS': {
        'driver': 'SQL Server Native Client 11.0',
    },
}
</pre>

就是这么简单。然后惯例 `./manage.py shell` 测试一下

<pre lang='python' line='1'>from django.db import connections
cur = connections['test'].cursor()
cur.execute("SELECT * FROM testtable")
cur.fetchone()
</pre>

如果能正常获得query结果说明一切正常。

因为我只是需要在一个APP的Views里通过 Raw SQL 来查询远程MSSQL的数据库，并不用在Model中使用它，所以并没有配置数据库路由，有需要的话可以参见Django的 <a href="https://docs.djangoproject.com/en/1.6/topics/db/multi-db/#topics-db-multi-db-hints" title="Django Multiple databases 参考手册" target="_blank">Multiple databases 参考手册</a>。

这个方法不仅适合MSSQL，对所有支持 ODBC 的 Database Server 应该都适用，说起来这都得感谢开放的微软同志呢。
