---
author: 摩摩诘
categories:
- 代码卷轴
date: 2021-01-07T00:00:00+08:00
tags:
- ansible
- python
title: 如何正常地在 Ansible Module 里访问 Ansible Facts
url: /articles/ansible-module-facts.html
draft: false

---

最近在写部署相关代码时需要使用 Ansible，于是研究了一下如何写 Ansible Collections。在实践过程中需要在 Ansible 模块中访问 Ansible Facts 来做一些条件判断，但是在[官方开发文档](https://docs.ansible.com/ansible/latest/dev_guide/index.html)中没有发现任何相关说明，搜索到的[ Stackoverflow 上的回答](https://stackoverflow.com/questions/45074728/use-ansible-facts-in-module-code)也比较违反常理，所以自己看了一下 Ansible 的源码，找到了一个比较正常的方式。

## Ansible 内置的 Facts 模块

既然要从模块里调用，那第一反应自然是直接调用 Ansible 里和 Facts 相关的 API。浏览代码库可知 Fact 相关的代码在 `lib/ansible/module_utils/facts` 目录下，比如我想获取操作系统信息，可以在自己的模块中导入 `lib/ansible/module_utils/facts/system/distribution.py` 中的 `Distribution` 类，然后调用相关方法即可。

```python
from ansible.module_utils.facts.system.distribution import Distribution

distribution = Distribution(module=module)
distro_facts = distribution.get_distribution_facts()
```

但并不是每一种 Fact 都有类似 Distribution 这样的 Class 可以直接调用，更何况我们更希望一次获取到所有自己需要的 Fact 字典，而不是每个 Fact 都自己写个实现。

## Setup 模块 和 FactCollector 类

深入调查得知，Fact 获取是通过一大波 FactCollector 类实现的。首先有一个 `BaseFactCollector` 基类，每一组 Fact 获取都是 `BaseFactCollector` 的实现，最后 Ansible 通过 `ansible.builtin.setup` 模块(`lib/ansible/modules/setup.py`)来执行和输出。

`ansible.builtin.setup` 模块中创建 Collectors 和获取 Facts 的方式如下。

```python
fact_collector = \
    ansible_collector.get_ansible_collector(all_collector_classes=all_collector_classes,
                                            namespace=namespace,
                                            filter_spec=filter_spec,
                                            gather_subset=gather_subset,
                                            gather_timeout=gather_timeout,
                                            minimal_gather_subset=minimal_gather_subset)

facts_dict = fact_collector.collect(module=module)
```

既然如此，那我们搞清楚 `get_ansible_collector` 方法各项参数的意义，然后在自己的模块里模仿一下就 OK 了。

## 如何在自己的模块里使用 Fact Collector

Ansible 所有的 FactCollector 可以在 `lib/ansible/module_utils/facts/default_collectors.py` 中找到，从对应的源文件中可以大致了解各自获取的目标 Fact。

`ansible.builtin.setup` 模块默认会执行所有符合目标 Platform 的 Collector，但是可以通过 `gather_subset` 参数来指定需要的 Collector 名，另外还能使用 `filter_spec` 参数来过滤结果。很多 Collector 并非调用系统 API，而是直接使用 Shell 脚本等方式来获取信息的，所以为了执行速度，我们最好仅仅指定那些自己需要的 Collector。

比如我只需要获取 主机名、操作系统、网络 这三类信息，可以指定 `gather_subset` 参数。

```python
collectors = default_collectors._base + default_collectors._network
gather_subset = ['platform', 'distribution', 'network']

fact_collector = \
    ansible_collector.get_ansible_collector(all_collector_classes=collectors,
                                            gather_subset=gather_subset)

facts = fact_collector.collect(module=module)
```

这样 Ansible 在执行这个模块时就只会获取这三种 Fact，然后就可以随意使用这些数据了。事实上，上述的 `all_collector_classes` 参数也可以直接使用默认的 Collectors（`default_collectors.collectors`），无需特别指定，不过限定之后可以让程序在匹配 Subset 时少跑几个循环，可能略微快那么一丢丢。

## 后话

作为一个自动化运维框架，「在第三方模块里直接有效地获取系统信息」这种需求应该是很基本的，照理官方文档会提及才对。不过就我这次的体验看，以 Ansible 的开发文档之杂乱，出现这种重要信息的缺失也是情理之中。比如官方文档中[开发环境配置的第一步竟然是 Clone 整个 Ansible Repo](https://docs.ansible.com/ansible/latest/dev_guide/developing_modules_general.html#environment-setup)，简直不敢相信，我是要写自己的 Module，不是要搞 Ansible 开发啊，何至于。
