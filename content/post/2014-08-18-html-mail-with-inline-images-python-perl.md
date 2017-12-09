---
title: Python/Perl 如何在HTML邮件正文中嵌入本地图片
author: 摩摩诘
type: post
date: 2014-08-17T16:21:02+00:00
excerpt: 发送包含有图片内容的HTML邮件是一个很普遍的需求，无论是写运维脚本还是网站后台都有可能碰到。前些天写一个脚本的时候仔细研究了一下，问题的关键在于如何在HTML邮件正文插入本地图片，而不是以附件的方式。
url: /articles/html-mail-with-inline-images-python-perl.html
index_image:
  - https://www.digglife.net/wp-content/uploads/2014/08/email.jpg
categories:
  - 代码卷轴
tags:
  - email
  - perl
  - python

---
发送包含有图片内容的 HTML 邮件是一个很普遍的需求，无论是写运维脚本还是网站后台都有可能碰到。前些天写一个脚本的时候仔细研究了一下，问题的关键在于如何在 HTML 邮件正文插入本地图片，而不是以附件的方式。

现在的一些多媒体邮件中的图片多以图片链接的形式嵌入，但是很多邮件客户端需要用户确定之后才能显示，而直接嵌入本地图片的方式，可以一定程度上避免。当然，这同样会造成邮件过大，如果发送次数非常频繁，可能也会给造成一些性能负担。

<!--more-->

### 邮件正文嵌入本地图片的原理

<a href="http://en.wikipedia.org/wiki/MIME#MIME_headers" title="MIME Wiki" target="_blank">MIME</a>(Multipurpose Internet Mail Extensions)协议支持在邮件头中指定各种类型的媒体文件，而邮件正文中则可以直接引用Header中定义的 Content-ID。以图片类型为例，MIME邮件头类似于：

```html
Content-Type: image/png; name="digglife.png"
Content-Disposition: inline; filename="digglife.png"
Content-Transfer-Encoding: base64
Content-ID: <digglife>
Content-Location: digglife.png
```

邮件正文中则可以这样引用，注意src的内容。

```html
<img src="http://digglife.qiniudn.com/qiniu/3851/image/0ee02217f49ca9475c28e137f414a71f.jpg" alt="digglife" />
```

所以，在 HTML 邮件正文中嵌入本地图片的问题就转换为，如何在程序中定义邮件头。

### 使用 Python 发送嵌入本地图片的邮件

[Python][1] 号称 Batteries Included ， 当然不是浪得虚名。内置的 <a href="https://docs.python.org/2/library/email.html" title="Python内置email模块" target="_blank">email</a> 模块就提供了丰富的接口，使用起来非常直观方便。

```python
from email.MIMEMultipart import MIMEMultipart
from email.MIMEText import MIMEText
from email.MIMEImage import MIMEImage
import smtplib

subject = 'May the Force Be With You!'
sendfrom = 'i@digglife.net'
sendto = 'anakin@tatooi.ne'
copyto = 'c3po@tatooi.ne'

msg = MIMEMultipart('related')
msg['Subject'] = subject
msg['From'] = sendfrom
msg['To'] = sendto
msg['CC'] = copyto

content = MIMEText('<img src="http://digglife.qiniudn.com/qiniu/3851/image/0ee02217f49ca9475c28e137f414a71f.jpg" alt="digglife" />')
msg.attach(content,'html'))

#二进制模式读取图片，并绑定到邮件头
fp = open('digglife.png','rb')
img = MIMEImage(fp.read())
img.add_header('Content-ID','digglife')
msg.attach(img)

smtp = smtplib.SMTP()
#连接本地SMTP服务器
smtp.connect('127.0.0.1')
smtp.sendmail(sendfrom, [sendto,copyto] ,msg.as_string())
```

上面的代码中使用的是本地 SMTP 服务器，在实际使用过程中，也可以指定远程 SMTP 服务器，比如[Gmail][2]，但需要定义用户名和密码。

唯一可惜的是，Python 没有内置的 HTML Temlate 模块，不然复杂的 HTML Code 也可以不用写在代码里了。

### 使用 Perl 发送嵌入本地图片的邮件

Perl 从来不说自己 Batteries Included，可是估计谁也不在乎这个，都习惯依赖 CPAN 了。一般我们用比较流行的 <a href="http://search.cpan.org/~rjbs/MIME-Lite-3.030/lib/MIME/Lite.pm" title="MIME::Lite模块" target="_blank">MIME::Lite</a> 模块来发送邮件，原理都是一样的。

```perl
use strict;
use MIME::Lite;

my $msg = MIME::Lite->new(
    From    => 'i@digglife.net',
    To      => 'anakin@tatooi.ne',
    Cc      => 'c3po@tatooi.ne',
    Subject => 'May The Force Be With You!',
    Type    => 'multipart/related'
);

$msg->attach(
    Type => 'text/html',
    Data => qq{

            <img src="http://digglife.qiniudn.com/qiniu/3851/image/0ee02217f49ca9475c28e137f414a71f.jpg" />

    },
);
$msg->attach(
    Type => 'image/png',
    Id   => 'digglife',
    Path => 'digglife.png',
);

$msg->send('smtp','127.0.0.1');
```

其实除了直接嵌入本地图片之外，还可以直接将本地图片转码成 base64 字符串直接写入 HTML 。但是很多邮件客户端并不支持 base64 作为 img 的 src ，所以并不推荐，这里略过不谈。

 [1]: https://www.digglife.net/articles/tag/python "Python相关文章"
 [2]: https://www.digglife.net/articles/tag/gmail "Gmail相关文章"
