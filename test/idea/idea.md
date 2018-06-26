6/25/2018 9:19:08 PM 

##（一） IntelliJ IDEA 介绍
IntelliJ IDEA 官网：[https://www.jetbrains.com/idea/](https://www.jetbrains.com/idea/)

IntelliJ IDEA 主要用于支持 Java、Scala、Groovy 等语言的开发工具

##（二）IDEA目录说明、VM 设置

![](https://i.imgur.com/rhwUeIo.jpg)
	
	idea.exe 文件是 IntelliJ IDEA 32 位的可行执行文件
	idea.exe.vmoptions 文件是 IntelliJ IDEA 32 位的可执行文件的 VM 配置文件
	idea64.exe 文件是 IntelliJ IDEA 64 位的可行执行文件
	idea64.exe.vmoptions 文件是 IntelliJ IDEA 64 位的可执行文件的 VM 配置文件
	idea.properties 文件是 IntelliJ IDEA 的一些属性配置文件

Help -> Edit Custom VM Options 来进行个性化配置

	 #4/8G内存机器的配置
	 -Xms128m
	 -Xmx750m
	 -XX:MaxPermSize=350m
	 -XX:ReservedCodeCacheSize=225m

	 #12/16G内存机器的配置
	 -Xms512m
	 -Xmx1500m
	 -XX:MaxPermSize=500m
     -XX:ReservedCodeCacheSize=500m

Help -> Edit Custom Properties 来进行个性化配置


	idea.config.path=${user.home}/.IntelliJIdea/config
	#该属性主要用于指向 IDEA 的个性化配置目录
	idea.system.path=${user.home}/.IntelliJIdea/system
	#该属性主要用于指向  IDEA的系统文件目录
	idea.max.intellisense.filesize=2500
	#该属性主要用于提高在编辑大文件时候的代码帮助	
	idea.cycle.buffer.size=1024
	#该属性主要用于控制控制台输出缓存。


##（三）idea常用设置
显示工具条
![](https://i.imgur.com/so08C2a.jpg)
主题字体修改
![](https://i.imgur.com/nLQPeA4.jpg)
代码编辑字体修改
![](https://i.imgur.com/iE6uQmI.jpg)
控制台输出字体修改
![](https://i.imgur.com/kRaLxhw.jpg)
文件编码修改
![](https://i.imgur.com/iJFHCDH.jpg)

##（四） Java 文件编译方式

![](https://i.imgur.com/ZjHK51C.jpg)

![](https://i.imgur.com/zfWJmbE.jpg)

##（五）运行web项目
IntelliJ IDEA 提供的体验是：一个 Project 打开一个 Window 窗口

一个 Project 可以有多个 Module



##（六）运行maven项目

