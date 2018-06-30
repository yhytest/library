3.1.LVS是什么

LVS即Linux虚拟服务器。

* LVS主要用于多服务器的负载均衡。
* 工作在网络层，实现高可用的服务器集群
* 把许多低性能的服务器组合成一个超级服务器。
* 配置非常简单，且有多种负载均衡的方法。
* 稳定可靠
* 可扩展性也非常好。

3.3.nginx和lvs作对比的结果：

* nginx工作在网络的应用层，主要做反向代理；   lvs工作在网络层，主要做负载均衡。
* nginx对网络的依赖较小，   lvs就比较依赖于网络环境。
* 一般最前端所采取的策略应是lvs。    nginx可作为lvs节点机器使用。

3.4.负载均衡机制
LVS的通过控制IP来实现负载均衡。IPVS是其具体的实现模块。

IPVS为此有三种机制：

* VS/NAT(Virtual Server via Network Address Translation)，即网络地址翻转技术实现虚拟服务器。
* VS/TUN（Virtual Server via IP Tunneling）,即IP隧道技术实现虚拟服务器。
* VS/DR（Virtual Server via Direct Routing），即用直接路由技术实现虚拟服务器。

![](https://i.imgur.com/wT7TrXz.png)
![](https://i.imgur.com/FL0axaC.png)