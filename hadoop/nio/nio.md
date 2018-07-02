## 2.1 NIO简介
nio 是New IO 的简称
	
* 为所有的原始类型提供(Buffer)缓存支持
* 字符集编码解码解决方案
* 支持锁和内存映射文件的文件访问接口
* 提供多路非阻塞式的高伸缩性网络I/O

## 2.2 socket io or socket nio 


## 2.3 io or nio 

使用传统的IO读取文件内容,会有较大的性能开销, 主要表现在一下两方面:

* 上下文切换 
* Buffer内存开销 

![](https://i.imgur.com/AKNwsQm.png)

* 先将文件内容从磁盘中拷贝到操作系统buffer
* 再从操作系统buffer拷贝到程序应用buffer
* 从程序buffer拷贝到socket buffer
* 从socket buffer拷贝到协议引擎

NIO直接将 read buffer 拷贝到 socket buffer.依赖于操作系统底层的sendFile()实现的.

![](https://i.imgur.com/Z6wtXJk.png)