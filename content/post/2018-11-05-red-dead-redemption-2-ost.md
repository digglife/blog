---
author: 摩摩诘
categories:
- 代码卷轴
date: 2018-10-24T11:00:00+08:00
tags:
- 游戏
- ps4
- 荒野大镖客2
- python
title: 荒野大镖客救赎 2 原声音乐
url: /articles/red-dead-redemption-2-ost.html

---

虽然在北国出差，到现在还无法玩到《荒野大镖客救赎 2》，但是可以先用原声带（OST）培养一下西部情绪啊！结果发现 Rockstar 至今还没**正式**发行原声带，而且连个预计发售日期都没有，这事儿办的可真的一点儿都不 Rock。
<!--more-->

但是，幸运的是，有朋友在 [YouTube](https://www.youtube.com/watch?v=8OpRKaa9eJY&t=605s) 上发布了可能是从游戏中转录/抓取的音轨，我听了一下，质量还不错，可以暂时解解馋。

YouTube 下载下来的音频是 OPUS 格式，而且是包含所有音轨的单一文件。这样如果我特别喜欢其中一首，想单曲循环就比较麻烦。好在上传者提供了文本时间轴，所以我写了一个 Python 脚本按照时间轴把这个文件分割成了独立的 MP3，而且打上了 ID3 标签（专辑名称、专辑封面、艺术家、年代、轨道编号等等），比较完美地模拟了专辑的效果。

![荒野大镖客救赎 2 原声音乐 iTunes 截图](/wp-content/uploads/rdr2-ost-itunes.png)


## 脚本源代码

[脚本的源代码放在了 GitHub 上](https://github.com/digglife/YTMusicSplit)。

基本原理是，读取时间轴文件，获取起止时间戳和标题，使用 MPV 命令行切割转码，然后使用 [eyeD3](https://github.com/nicfit/eyeD3) 模块来添加 ID3 标签。

理论上，类似这种有明确的时间轴，需要将一整个音频文件做分割的情况都可以使用。不过我暂时也只用了两次，一次是《荒野大镖客救赎2》，一次是《Ruiner》。


## 关于 eyeD3 模块的笔记

### 添加专辑封面的 API

直接用 MPV 分割出来的 MP3 文件没有任何 Metadata，这样在播放器里显示得就不太整洁，而且也不够美观。所以找到了 eyeD3 这个模块给每个音轨加 ID3 标签。API 是很直观的：

```python
import eyed3

audiofile = eyed3.load("song.mp3")
audiofile.tag.artist = u"Integrity"
audiofile.tag.album = u"Humanity Is The Devil"
audiofile.tag.album_artist = u"Integrity"
audiofile.tag.title = u"Hollow"
audiofile.tag.track_num = 2

audiofile.tag.save()
```

但是上面的代码里，并没有提到添加专辑封面这个比较重要的 API，我猜测是因为这个 API 的参数相对比较复杂。

```python
def set(self, type_, img_data, mime_type, description=u"", img_url=None):
```

一共有 5 个参数之多，而且文档里并没有详细说明，只能看看源码。

| 参数 | 解释 |
|--------|-----------|
|`type_`  |图片的类型，[ID3 定义的有 21 种之多](https://github.com/nicfit/eyeD3/blob/v0.8.7/src/eyed3/id3/frames.py#L487-L507)，真是大开眼界 |
|`img_data` | 图片的二进制数据 |
|`mime_type`| 图片的 MIME 类型，可以用 `eyed3.utils.guessMimetype` 函数从文件名获取 |
|`description` | 图片的说明，可为空 |
|`img_url` | 图片的链接，如果指定 URL，则 `img_data` 和 `mime_type` 均可为空 |

于是如果接着上面的例子，可以这么写。

```python
img = '/path/to/cover.jpg'

audiofile.tag.images.set(
    3, #FRONT_COVER
    open(img, 'rb').read(),
    eyed3.utils.guessMimetype(img),
    'ALBUM_COVER' #DESCRIPTION
)

audiofile.tag.save()
```

### Logging 设置引发的血案

在写这个脚本的过程中，我发现自己的 log 怎么设置都无法正常输出，最后才发现是 eyeD3 模块作者挖的一个坑。

他在 `eyed3.utils.log` 子模块的全局 scope 中调用了 `logging.basicConfig()` 初始化 log 设置，这样所有输出都会导入到 `stderr` 里，我即便重新调用 `basicConfig` 都没用。

有人提了 [issue](https://github.com/nicfit/eyeD3/issues/243)，作者也改过了，不过没有 release，所以 PyPI 上也还是有问题的代码，不知道还会坑多少人😁。

## 荒野大镖客救赎 2 原声音乐 下载

分割出来的原声 一共 25 个 MP3 文件，上传到了百度盘。

```
链接:https://pan.baidu.com/s/1pSIasGiUJpN8fOYbf6hRRg
密码:lmkq
```
