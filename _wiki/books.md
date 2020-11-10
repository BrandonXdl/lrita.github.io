---
layout: wiki
title: 编程书籍/文档
categories: program books
description: 编程书籍/文档
keywords: 编程书籍/文档
---

# assembly

- [X86 汇编简介](/images/posts/tools/CS356Unit4_x86_ISA.pdf)

# cpp

- [cmake 实践](/images/posts/cplusplus/CMake-Practice.pdf)
- [精通 cmake](/images/posts/cplusplus/mastering-cmake.pdf)
- [如何使用 identity 元函数禁止模板自动推导](/images/posts/cplusplus/the-identity-metafunction.pdf)
- [INTRODUCTION TO LLVM](/images/posts/cplusplus/19_LLVM.pdf) LLVM 的基本介绍，组成部分，编译流程，LLVM Pass
- [ELF Handling For Thread-Local Storage](/images/posts/cplusplus/ELF_Handling_For_Thread-Local_Storage.pdf) 讲解线程本地存储在不同平台、不同场景下内部的实现。

# go

- [go tool trace](/images/posts/go/Rhys-Hiltner-go-tool-trace-GopherCon-2017.pdf)

# rust

- [在 Mac 下面调优 TiKV](https://www.jianshu.com/p/a80010878def) MacOS 下调优 RUST 的方法

# linux

- [深度分析 Linux 下双网卡绑定七种模式](/images/posts/linux/深度分析Linux下双网卡绑定七种模式.pdf)
- [Linux High Loadavg Analysis](http://oliveryang.net/2017/12/linux-high-loadavg-analysis-1/) 如何理解 CPU load 的含义，如何排查 load 增高的原因。此方面讲解最全面、最详细的一篇文章。
- [Linux 内幕](https://0xax.gitbooks.io/linux-insides/content/)

# 文件系统

- [Linux 文件空洞与稀疏文件](/images/posts/filesystem/Linux_File_Hole_And_Sparse_Files.pdf) 讲解 linux 文件系统下文件空洞与稀疏文件
- [Linux 内核文件 Cache 机制](/images/posts/filesystem/Linux.Kernel.Cache.pdf)
- [Linux 内核写文件过程](/images/posts/filesystem/Linux.Kernel.Write.Procedure.pdf)
- [Linux 内核延迟写机制](http://www.ilinuxkernel.com/files/Linux.Kernel.Delay.Write.pdf)
- [Linux 通用块设备层](/images/posts/filesystem/Linux.Generic.Block.Layer.pdf)
- [Linux 内核 IO 调度层](/images/posts/filesystem/Linux.Kernel.IO.Scheduler.pdf)
- [Linux 内核读文件过程](/images/posts/filesystem/Linux.Kernel.Read.Procedure.pdf)

# 调优诊断

- [看懂 vmstat/mpstat 数据诊断](/images/posts/filesystem/Extreme-Linux-Performance-Monitoring-and-Tuning.pdf)
- [Linux CPU 占用率原理与 精确度分析](/images/posts/linux/Linux_CPU_Usage_Analysis.pdf)
- [震惊，用了这么多年的 CPU 利用率，其实是错的](https://mp.weixin.qq.com/s/KaDJ1EF5Y-ndjRv2iUO3cA)：如何正确理解 CPU 使用率，找到系能问题所在。
- [Linux Systems Performance in 50 mins](/images/posts/linux/Percona2016_LinuxSystemsPerf.pdf)
- [Linux Performance Tools](/images/posts/debug/Linux.Performance.Tools.Oct.2014.pdf) 主要讲 Linux 系统各方面都有哪些 debug 工具（观察、系能压测、调优、统计）、debug 方法论
- [Linux Performance Tools - 2015](/images/posts/debug/velocity2015linuxperftools-150527215912-lva1-app6891.pdf) 主要讲 Linux 系统各方面都有哪些 debug 工具，其中内容比 👆 更丰富一点。

## 火焰图

- [Blazing Performance with Flame Graphs](/images/posts/debug/LISA13_Flame_Graphs.pdf) 火焰图入门，教如何看图、生成图
- [Linux CPI FlameGraph](http://oliveryang.net/2018/03/linux-CPI-flamegraph/) 识别负载类型(CPU/MEMORY Bound) 当 CPU 使用率高时，CPU 行为分析，哪些 stall 行为在浪费 CPU。如何生成 CPI 火焰图，如何看图。
- [Linux Profiling At Netflix](/images/posts/debug/Linux.Profiling.at.Netflix.Feb.2015.pdf) 如何使用`perf`，可能会遇到哪些问题（栈损坏\符号丢失），如何修复它们。

## SystemTap

- [Using SystemTap with Linux](/images/posts/systemtap/Using-SystemTap-with-Linux.pdf) SystemTap 入门，将一些基本的语法、数据结构

# 分布式原理

- [分布式系统一致性的发展历史 (一)](https://danielw.cn/history-of-distributed-systems-1) 本文的目的就是带你回顾从 70 年代起, 到如今百花齐放的分布式系统中一致性问题的发展和演化，主要讲分布式时序以及线性一致性和顺序一致性
- [分布式系统一致性的发展历史 (二)](https://danielw.cn/history-of-distributed-systems-2) 根据分布式故障作为引子，讲述分布式共识的历史。
- [请不要再称数据库是 CP 或者 AP](https://blog.the-pans.com/cap/) 讲解 CAP 的真实含义及其讨论范围，及其为什么在网络分区的情况下，我们要放弃可用性和一致性中的一个。
- [awesome-distributed-systems](https://github.com/rShetty/awesome-distributed-systems) 分布式博库、论文集合

## DHT/数据分布

- [一致性哈希算法（一）- 问题的提出](https://writings.sh/post/consistent-hashing-algorithms-part-1-the-problem-and-the-concept) 连续四篇，从原理出发，举例几种一致性哈希算法，研究其均匀性与一致性。图文并茂，讲解细致。
- [一致性哈希算法（二）- 哈希环法](https://writings.sh/post/consistent-hashing-algorithms-part-2-consistent-hash-ring)
- [一致性哈希算法（三）- 跳跃一致性哈希法](https://writings.sh/post/consistent-hashing-algorithms-part-3-jump-consistent-hash)
- [一致性哈希算法（四）- Maglev 一致性哈希法](https://writings.sh/post/consistent-hashing-algorithms-part-4-maglev-consistent-hash)

# database

- [基于混合逻辑时钟的分布式事务实现深度剖析](/images/posts/database/基于HLC的分布式事务实现深度剖析.pdf) 讲述数据库为什么需要时钟，在分布式环境下如何解决时钟，对比优劣。
- [数据库系统的优化与调优：从理论到实践](/images/posts/database/数据库系统的优化与调优：从理论到实践.pdf) 讲述了从串行和并行的角度如何优化。排队论揭示优化的上限。以及在 MySQL 中的一些实践，以及结合硬件特性的一些优化案例。
- [利用新硬件提升数据库性能.pptx](/images/posts/database/利用新硬件提升数据库性能.pptx)
- [数据库管理系统架构](/images/posts/database/Architecture-of-a-Database-System.pdf) 本文翻译自经典英文论文《Architecture of a Database System》，原文作者是 Joseph M. Hellerstein, Michael Stonebraker 和 James Hamilton。该论文可以作为中国各大高校数据库实验室研究生的入门读物，帮助学生快速了解数据库的内部运行机制。
- [Oceanbase 内存事务引擎](/images/posts/database/OceanBase-memory-transaction-engine.pdf) 粗略讲解了一下 Oceanbase 的事务引擎如何工作，处理事务并发、实现不同的事务隔离级别、并发事务回放等。
- [闪存数据概念与技术](/images/posts/database/flash_database_book.pdf) 介绍 SSD、Flash 特性和技术特点，以及针对其特点的数据技术。
- [Dynamo: Amazon's Highly Available Key-value Store(中文译本)](https://arthurchiao.github.io/blog/amazon-dynamo-zh/)
- [Bigtable: A Distributed Storage System for Structured Data (中文译本)](https://arthurchiao.github.io/blog/google-bigtable-zh/)
- [Ceph: A Scalable, High-Performance Distributed File System (中文译本)](https://arthurchiao.github.io/blog/ceph-osdi-zh/)

### mysql

- [深入解析 MySQL replication 协议](https://www.jianshu.com/p/5e6b33d8945f)

### canssandra

- [CASSANDRA 实战](/images/posts/database/canssandra/CASSANDRA实战[白色].pdf)
- [Cassandra 权威指南](/images/posts/database/canssandra/Cassandra权威指南.pdf)

### clickhouse

- [MySQL-DBA 解锁数据分析的新姿势-ClickHouse-新浪](/images/posts/database/clickhouse/MySQL-DBA解锁数据分析的新姿势-ClickHouse-新浪.pdf)

# 数据结构

- [Spin](http://spinroot.com/) 一个形式化验证多线程数据结构的工具
- [优化的 LRU 算法：Outperforming LRU with an Adaptive Replacement Cache Algorithm](/images/posts/datastructure/ARC.pdf)
- [各种数据结构的可视化展示](https://www.cs.usfca.edu/~galles/visualization/Algorithms.html)
- [Dynamic-Sized-Nonblocking-Hash-Tables](/images/posts/datastructure/Dynamic-Sized-Nonblocking-Hash-Tables.pdf), [PPT](/images/posts/datastructure/Dynamic-Sized_Nonblocking_Hash_Tables.pptx) 一种支持动态调整 bucket 大小，存储元素无限制的并发哈希表，但是其 bucket 层面可以做到 lockfree，但是 bucket 内部需要采用其他数据结构保证 lockfree。
- [Log Structured Merge Tree](/images/posts/database/lsmtree-170129180333.pdf) 介绍`Log Structured Merge Tree`的历史以及原理。
- [现代数据库背后的算法](/images/posts/datastructure/Algorithms_Behind_Modern_Storage_Systems.pdf) 主要介绍 B-TREE 和 LSM 算法，并进行对比。哈佛大学的 DASlab(Data System Laboratory)研究员总结数据库系统三个关键优化因子是：_read overhead(read optimized)_，*update overhead(write optimized)*和*memory overhead(space optimized)*，简称*RUM*，对于一个数据库系统，最多只能将其中一项优化到极致，即另两项必须付出代价，比如 LSM，追求写优化(所以操作都是顺序写，更新操作效率高)，就得付出读放大、空间放大的代价（写放大来自于*compaction*，是优化读性能的代价）。

# API 设计

- [GRPC API Design Guide](https://cloud.google.com/apis/design/)

# 数学理论

- [排队论及其应用浅析](/images/posts/math/排队论及其应用浅析.pdf)
- [排队论](http://netedu.xauat.edu.cn/jpkc/netedu/jpkc/ycx/kcjy/kejian/pdf/09.pdf)

# 工具

- [latex 入门-简版-刘海洋](/images/wiki/latex入门-简版-刘海洋.pdf)
- [SRE-Google 运维解密](/images/blog/SRE-Google.pdf)
- [SRE 工作手册（google 开源书）](/images/posts/com/the-site-reliability-workbook-next18.pdf)
- [给 TiKV 开发 Grafana 的 datasource](https://www.jianshu.com/p/057fe9e57274) 资源提供 API 配合 Grafana，提供监控的新思路
- [硬件体系架构浅析](/images/posts/tools/硬件体系架构浅析.pdf) 简介常用硬件体系、特点、基本数据、性能指标
- [现代网络负载均衡与代理导论](https://arthurchiao.github.io/blog/intro-to-modern-lb-and-proxy-zh/) 充分了解负载均衡的实质与效用
