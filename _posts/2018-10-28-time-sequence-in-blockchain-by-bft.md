---
layout: post
title: 使用PBFT和Vector Clock解决区块链时序问题
categories: [blockchain]
description: blockchain
keywords: blockchain
---

# 背景
如果用区块链来记账，就会涉及到一个分布式时序的问题。当交易在不同区块时，我们很容易依赖各自相关的块高度来判断时序问题。但是为了提高区块链的吞吐，就必须进行批出来，这样一来，出块的间隔就会增大，如果相关的两个事件，事件间隔特别短，出现在同一个块内时，如果判断时序问题？因为通常的P2P传播很容易乱序，同时出块的节点地理位置漂移很大，我们无条件信任出块节点的排序？我想一般场景可以这样，对时序非常敏感的场景就不能这样信任某一个节点的排序了。

# 为什么用PBFT
为了解决时序问题，那么我们就需要对每个交易产生的时间达成一个共识，这里我们使用`PBFT`[^1]，其比`DPOS`、`POW`等共识算法的优势就是：
* 在共识过程中，其能第一时间将交易传播到主要节点上，这是`DPOS`、`POW`等不具备的。这是非常重要的，如果自己都不能第一时间收到交易，那还怎么参与共识？只能条件信任他人了。
* 它能够实时识别作弊者，并且可以实时纠错和惩罚。`DPOS`、`POW`等都是后知后觉的，而且惩罚滞后的，有些都放弃了惩罚，依赖博弈论使其放弃作弊，然后博弈论需要每个参与者都是`精致的利己主义者`，然后在`EOS`运行这么久后，博理论并不能100%发挥其上帝法则，因为愚昧的大多数，其每一个决策并不一定有正收益，反而被各种集体利用蛊惑。
* `PBFT`其通讯复杂度是$$O(n^2)$$，并且需要一个确定是参与者范围，比较适合联盟链场景。

# 时序逻辑
首先，每个参与者各自维护一个本地单调时钟，该单调时钟基于物理时钟，但是不能回退。然后每个参与者维护一个`Vector`，记录着每个参与者的时间戳，初始值可以都为零。比如我们有4个参与者$$P_1$$、$$P_2$$、$$P_3$$、$$P_4$$：

![](/images/posts/blockchain/vector-clock-pbft-0.png)

`PRE-PREPARE`：当有客户端请求$$Tx_A$$到达时，$$P_1$$节点在将当前时间戳$$t_{A1}$$添加到$$Tx_A$$中并且进行签名。然后将$$Tx_A$$发送给各个参与者，收到$$Tx_A$$的参与者，验证前面合法性、验证$$P_1$$时间戳的单调性，并且将时间戳$$Tx_A$$记录到本地。

![](/images/posts/blockchain/vector-clock-pbft-1.png)

`PREPARE`：如果都OK，各自将本地的时间戳都附加到$$Tx_A$$上，并且签名，然后发送给各个参与者。

![](/images/posts/blockchain/vector-clock-pbft-2.png)

每个参与者收到其他人的消息后，根据交易信息进行合并，校验各个参与者的时间单调性、签名等，此时，每个参与者的本地都收集到一个关于交易$$Tx_A$$的一个`Vector Clock`$$[T_{P_1} = t_{A1},T_{P_2} = t_{A2},T_{P_3}=t_{A3},T_{P_4}=t_{A4}]$$。这里我们忽略掉`COMMIT`阶段，因为我们需要收集每个参与者的时序，如果还需要其他行为，可以继续`COMMIT`阶段。

![](/images/posts/blockchain/vector-clock-pbft-3.png)

`REPLY`：我们可以选用$$Reply_i$$或者$$Reply_j$$方案，区别就是是否响应发起者。

## 比较逻辑
根据上面的流程，我们对于每个交易$$Tx_i$$都会有一个对应的`Vector Clock`$$[T_{P_1} = t_{i1},T_{P_2} = t_{i2},T_{P_3}=t_{i3},T_{P_4}=t_{i4}]$$。

当任意两个交易$$Tx_i$$和$$Tx_j$$有$$\forall\ p\in{P}: T_i[p] < T_j[p]$$，则表示$$Tx_i$$发生在$$Tx_j$$之前[^2]。

# 参考
[^1]: [Practical Byzantine Fault Tolerance](http://pmg.csail.mit.edu/papers/osdi99.pdf)
[^2]: [Lamport's Logical Clocks 和 Vector Clock](https://lrita.github.io/2018/10/24/lamport-logical-clocks-vector-lock/)