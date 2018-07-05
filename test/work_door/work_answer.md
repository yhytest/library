  ##（一）database测试笔试题

* can the value of primary key be NULL? no
* Is the index used to improve the peformance? yes
* is the keyword “select distinct” used to group result-set by one or more columns? no
* which keyword is used to sort the result-set? order by
* which keyword is used to modify the existing records in table? update
##（二）python测试笔试题1
* which function is usd to get type of a variable? type
* which function is used to list all names of a class’s attributes? dir
* is the methods format used to get rid of blank space around a string? no
* can a class inheritance from multiple classes? yes
* which function is used to get the length of a string? len

##（三）java测试笔试题1
* can keyword final be assigned to a class? yes
* Can a java class inheritance from multiple classes?no, how about a java class implement multiple interfaces? yes
* Can a constructor be overrided?  no ,how about oveload? yes
* what is the Exception class inhertanced from? Throwable
* Could a static method call a non-static method in the same class? no

##（四）seleniuim面试题1

selenium中如何判断元素是否存在？

selenium中没有提供原生的方法判断元素是否存在，一般我们可以通过定位元素+异常捕获方式判断

如何提高selenium脚本的执行速度？

    使用效率更高的语言，比如java执行速度就快过python
    不要盲目的加sleep，尽量使用显式等待
    
用例在运行过程中经常会出现不稳定的情况，也就是说这次可以通过，下次就没办法通过了，如何去提升用例的稳定性？

    测试专属profile，尽量让静态资源缓存
    尽量使用显式等待
    尽量使用测试专用环境，避免其他类型的测试同时进行，对数据造成干扰

你的自动化用例的执行策略是什么？

    每日执行：比如每天晚上在主干执行一次
    周期执行：每隔2小时在开发分之执行一次
    动态执行：每次代码有提交就执行


id,name,clas,xpath, css selector这些属性，你最偏爱哪一种，为什么？
xpath和css最为灵活

selenium的原理涉及到3个部分，分别是

    浏览器
    driver: 一般我们都会下载driver
    client: 也就是我们写的代码

	client其实并不知道浏览器是怎么工作的，但是driver知道，
	在selenium启动以后，driver其实充当了服务器的角色，
	跟 client和浏览器通信，client根据webdriver协议发送请求给driver
	，driver解析请求，并在浏览器上执行相应的操作，并把执 行结果返回给client。
	这就是selenium工作的大致原理。


什么是断言？可以简单理解为检查点，就是预期和实际的比较


你觉得自动化测试最大的缺陷是什么？
实现成本高,运行速度较慢,需要一定的代码能力才能及时维护




##（五）说一个你工作中有价值的bug

* 了解你平时工作中的测试能力
* 考察你的表达能力
* 也许就是想抛一个问题给你，自己好有时间继续看你的简历。


##（六）软件测试综合笔试题

你认为测试工程师应该掌握哪些技术，其中有哪些是你已经掌握的？
![](https://i.imgur.com/aKyToBY.png)
状态码分类和含义:

* 1xx： 指示信息：表示请求已接收， 继续处理。
* 2xx： 成功：表示请求已被成功接收、 理解、 接受。
* 3xx： 重定向：要完成请求必须进行更进一步的操作。
* 4xx： 客户端错误：请求有语法错误或请求无法实现。
* 5xx： 服务器端错误：服务器未能实现合法的请求。

简单解释以下专业术语：

* LAMP：Linux + Apache + MySQL + PHP (PHP开发经典架 构)                      
* Nginx：是一个高性能的HTTP和反向代理服务器。                
* Firebug：firefox下的一个扩展插件，能够调试所有网站语言。
* Bluetooth：蓝牙，是一种无线技术标准。                
* WiFi：Wi-Fi是一种允许电子设备连接到一个无线局域网（WLAN）的技 术。                   
* NFC：近场通信（Near Field Communication,NFC）是一种短距高频的无线电技术。
* LVS：是Linux Virtual Server的简写，Linux虚拟服务器。

##（七）

##（八）

##（九）

##（十）