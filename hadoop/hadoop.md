# HADOOP 分布式系统 云计算简介
-------------------------------
##（一）HADOOP背景介绍
1. HADOOP是apache旗下的一套**开源软件平台**
2. HADOOP提供的功能：利用服务器集群，根据用户的业务逻辑，对海量数据进行分布式处理
3. HADOOP的核心组件有
	* HDFS（分布式文件系统）
	* YARN（运算资源调度系统）
	* MAPREDUCE（分布式运算编程框架）
##（二）HADOOP产生背景
HADOOP最早起源于Nutch。Nutch的设计目标是构建一个大型的全网搜索引擎，实际中遇到拓展性问题——如何解决数十亿网页的存储和索引问题。
##（三）HADOOP与云计算
HADOOP则是云计算的PaaS层的解决方案之一
##（四）HADOOP应用案例
* 数据服务基础平台建设
* 用户画像
* 网站点击流日志数据挖掘
##（五）HADOOP生态圈
![](https://i.imgur.com/xAPuIMJ.png)

* HDFS：分布式文件系统
* YARN：运算资源调度系统
* MAPREDUCE：分布式运算程序开发框架
* HIVE：基于大数据技术（文件系统+运算框架）的SQL数据仓库工具
* HBASE：基于HADOOP的分布式海量数据库，离线分析和在线业务通吃
* ZOOKEEPER：分布式协调服务基础组件
* Mahout：基于mapreduce/spark/flink等分布式运算框架的机器学习算法库
* Oozie：工作流调度框架
* Sqoop：数据导入导出工具
* Flume：日志数据采集框架
* Ambari：基于Web 的工具，用于配置管理和监控的 Apache Hadoop 集群
* Avro：数据序列化系统。
* Cassandra：可扩展的、无单点故障的多主数据库。
* Chukwa：数据采集系统，用于管理大型分布式系统。
* HBase：一个可扩展的分布式数据库，支持结构化数据的大表存储。
* Hive：数据仓库基础设施，提供数据汇总以及特定的查询。
* Mahout：一种可扩展的机器学习和数据挖掘库。
* Pig：一个高层次的数据流并行计算语言和执行框架。
* Spark：Hadoop 数据的快速和通用计算引擎。
* TEZ：通用的数据流编程框架，建立在 Hadoop YARN 之上。
* ZooKeeper：一个高性能的分布式应用程序协调服务。
##（六）分布式系统
利用多个节点共同协作完成一项或多项具体业务功能的系统就是分布式系统

举例：solrcloud 

* 一个solrcloud集群通常有多台solr服务器
* 每一个solr服务器节点负责存储整个索引库的若干个shard（数据分片）
* 每一个shard又有多台服务器存放若干个副本互为主备用
* 索引的建立和查询会在整个集群的各个节点上并发执行
* solrcloud集群作为整体对外服务

分布式应用系统模拟开发
![](https://i.imgur.com/CwKnM4u.png)

##（七）云计算

## 云计算简介

###1.定义
* “云”其实是互联网的一个隐喻
* “云计算”其实就是使用互联网来接入存储或者运行在远程服务器端的应用，数据，或者服务。

###2.分类IaaS，PaaS和SaaS
* Infrastructure（基础设施）-as-a-Service，
* Platform（平台）-as-a-Service，
* Software（软件）-as-a-Service。

IaaS: Infrastructure-as-a-Service（基础设施即服务）硬件外包

PaaS: Platform-as-a-Service（平台即服务）中间件服务

SaaS: Software-as-a-Service（软件即服务）消费服务

![](https://i.imgur.com/0mFhIY5.png)