---
author: 摩摩诘
categories:
- 代码卷轴
date: 2017-12-15T13:45:12+08:00
tags:
- puppet
- 运维
- ruby
title: 混乱的 Puppet
url: /articles/puppet-chaos.html

---

### 混乱的 Puppet

大概在2015年的时候，我还在搞运维开发，当时选择了 Puppet(ver.3) 作为自动化运维框架，并在随后的一年里写了不少模块，甚至还给 Puppet 提过两个有效 Pull Request。后来我发现 Puppet 是那种比较典型的经不起细看的技术，乍一看优点很多，OS 支持全面、DSL 语法简单、易于扩展、第三方模块多、还特么提供了 HTTP API，但深入研究之后就会发现浑身都是洞。事隔四年，我又因为工作需要重新看了一下最新的 Puppet 6，发现这个项目的混乱程度有增无减，遂吐槽一篇。

1. DSL 让事情变得更复杂

   Puppet 的团队大概是为了照顾不懂开发的运维人员，所以用 Ruby 造了一个 DSL(即所谓 Puppet Language)，咋一看语法挺简单，门槛很低，极易上手，其实碰到稍微复杂一点的需求就捉襟见肘。为了弥补这一点，Puppet 又提供了 `Custom Functions`、`Custom Type` 和 `Custom Provider` 这三种扩展，使用 Ruby 编写，用于增强 Puppet 语法的表达力，但很多都是在重复实现那些通过 Ruby 本身可以更容易做到的事情。即便没用过 Puppet，看一下它的 标准库([`stdlib`](https://github.com/puppetlabs/puppetlabs-stdlib)) 就能明白这一点，整个模式大概就是——用 Ruby 实现一个 DSL，然后再用这个 DSL 反过来实现 Ruby 的一些语法糖。

   更显而易见的是，如果用户已经能运用 Ruby 来扩展，何苦要重新学习一个语法并不简洁统一的语言呢？

   现如今 Puppet 语言还加了很多时髦的特性，比如支持所谓「静态类型」等，Custom Function 都能用 Puppet 语言直接写，但是这反倒让我觉得坑挖得更深了。

2. 拉取模式带来很多问题

   Puppet 的核心是 客户端/服务端 模式（亦即所谓 CS模式），也就是客户端定时发送本机信息到服务端，获取配置，然后在本地应用的模式。这个模式，最大的特点在于「状态定义」，也就是你在服务端是在给所有机器定义一种目标状态。很多其他自动化运维工具，更多地是在做「行为定义」，也就是定义针对客户端做什么操作。

   但是这种客户端定期拉取的模式，很难满足如今大部分运维场景的需求，客户端是否每次都准确应用了我定义的状态，有没有出现异常，没有一个直接有效的方式。有时我们会通过 Custom Fact 收集客户端的信息来判断，但是这种反馈又会滞后。

   当然 Puppet 还提供了 MCollective 、Bolt 两种推送模式的工具，但始终不是它的强项。

3. 技术栈混乱

   Puppet 原本是一个 Ruby 项目，照说技术栈几乎都是 Ruby 系的，但一开始 PuppetDB 就用的 Clojure（运行在 JVM 上的 LISP），这就比较怪了。

   Facter 模块本来也是用 Ruby 实现的，后来觉得性能有问题，Facter 3 用 C++ 重写了，废掉了不少 Ruby API，如今似乎又觉得 C++ 让贡献代码的门槛变得过高，又想重新用回 Ruby，开了个项目叫 Facter-ng（Next Generation，开源世界的命名滥觞了，动辄NG），不知道什么时候又会切过去。

   Puppet Server 和 Puppet Agent 以前都是运行在 Ruby 默认的运行时 MRI 上的，如今为了性能，Server 用又特么用 Clojure 重写了，Ruby 的运行时也自然换到了 JVM ，但 Client 端还是 MRI，于是用户在编写代码的时候，还要小小地担心一下运行时不同的问题。

   从这几件事上能看出 Puppet 的技术团队总是想通过更换语言来解决性能问题，我猜他们要么经常更换 CTO，要么 CTO 是个愤青。

当年我在每天和 Puppet 打交道时，踩了很多坑，但现在只想到了上面这三点，有空再吐。

那么既然 Puppet 这么破，自动化运维框架哪家强呢？Ansible？Saltstack？Chef？我的建议是，不要搞运维😂。

