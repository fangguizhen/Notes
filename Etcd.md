[TOC]

# Etcd

Etcd是一个开源的、分布式的键值对数据存储系统。

用于存储key-value键值对，同时它不仅仅是存储，它主要用途是提供共享配置及服务发现（后面这两个特征非常有特点，主要用于container中），对于leader的选举非常优秀，他的leader选举更换对于前端是无感知的。运用容器读写数据在etcd上，除此还有支持快照及查看历史事件的功能。



## 主要功能介绍

* 键值写入与读取

* 过期时间

* 观察者（事件通知、状态变换等场景）

* 租约

* 集群管理相关操作

* 维护操作

* 用户及权限管理