[TOC]

## HBase 基础知识

### 两张特殊表

> 在旧版中：

1. -ROOT- 表: 记录了.META.表的region信息，-ROOT-只有一个region；
2. .META. 表: 记录了用户创建的表 的region信息，.META.可以有多个region；

> 在新版中：


zookeeper记录了-ROOT-的location（位置）信息；

客户端初次访问数据时（尚未缓存），访问流程:

client ==> zk ==location==> -ROOT- ==region==> .META. ====> userdata 