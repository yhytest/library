##（一）JUnit 介绍
**什么是 JUnit？**

单元测试：可以对重要的程序分支进行测试以发现模块中的错误。

单元测试框架：可以帮助我们完成自动化测试

Junit 官网：http://junit.org/

JUnit 是一个编写可重复测试的简单框架。它是单元测试框架的 xUnit 架构的一个实例。

--------------------

##（二）JUnit 安装

1、下载 junit-4.12.jar 文件：https://github.com/junit-team/junit4/releases

2、 打开 IntelliJ IDEA ，菜单栏：File菜单 –> Porject Structure 选项 –> Dependencies 标签 –> 点击 “+” 号 –> Library… –> Java 。 选择下载的 junit-4.12.jar 进行添加。

![](https://i.imgur.com/t4JZBQP.png)

3、以同样的方式下载和导入 hamcrest： 推荐使用maven下载jar包，然后添加如下核心包,否则，你将无法运行 Junit 单元测试。

hamcrest-core-1.3.ORC2.jar：hamcrest的核心包，使用hamcrest框架必须引入的包。（junit官方给的包就包含了该包）

hamcrest-library-1.3.ORC2.jar：包含各种断言，补充hamcrest core包中的断言。

这次我们从中选两个：hamcrest-core-1.3.jar和hamcrest-library-1.3.jar


    <dependency>
	<groupId>org.hamcrest</groupId>
	<artifactId>hamcrest-all</artifactId>
	<version>1.3</version>
	<scope>test</scope>
	</dependency>