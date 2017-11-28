---
layout: post
title: Telematik(计算机通信与网络 协议)
category: Post
---
Telematik 计算机通信与网络

这门课不能系统地复习到计算机网络的知识，但是可以利用设置的切入点，加深对网络层次实现的感觉。
比如，流控制，拥塞控制，现在应该可以重新认识。

列举不熟悉的节点：
TCP-Tahoe 协议
reno
等等

2017-10-31-第一章-基本传输拥塞问题
网络通信里面设置了“包”(Packet)为最基本的单元，进行传输。
传输每个Packet遇到路口，多个包只能走一个。

所以对于路口(Router)或者传输发起者(Sender)设置缓冲区域(Buffer)。传输不了的Packet暂时放在Buffer。

先观察静态拥塞窗口(Congestion Window)，拥塞崩溃情景(Congestion Collapse)。
实际信息发收总量(Goodput)跟所在小范围网络负载的衰减关系：
线性，然后越来越慢，最后断崖衰减。

![Telematik]({{ "/_images/telematik-001.jpg" | absolute_url }})

Congestion Reason(拥塞出现的原因)
一是原协议标准，收端容量设定小
二是不知道网络实时状态，负载，不能设定值(那么只能人为设计出估测方法，预判极端情况先兆)
流式数据(不是包)窗口小，网络负载 > 网络容量

解决：
预测一般拥塞，大部分提前处理；特殊情况，设计拥塞状态下的传输策略
两个点。Knee和Cliff
分布式处理，自下而上，收发端自行控制，彼此之间不用通信。

关于Optimization Criteria(优化依据)

Efficiency 
~由网络中最低数据传输率的结点影响。数据量求和的值要趋近网络的容量

Fairness
~决定传输的概率分配(1,1/N)，数据率确定

Convergence
~负载趋向定值的平滑区间，稳定变化

Distributedness
~分布式调节，每个网络节点优化的行为应该是自下而上、相互独立，不需要知道其他源的状态。

具体到方法：
Cwnd 设置拥塞窗口，窗口大小怎么定，动态变化怎么定
rate 数据率
End-2-End 端到端的控制
Network Hop-2-Hop 每一跳的控制
Router 路由中心化

然后又是一个重复的关键知识体系：TCP-Tahoe
Staukontrollfenster 拥塞窗口



路由器设置缓冲 Buffer 延迟 Latency
例：
Congestion Control(拥塞控制)


2017-11-01
课堂提问 重传机制

丢包 重传位置
