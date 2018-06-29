##（一）Hello World
新建名为print\_report.py的文本文件,并添加注释

注释：帮助理解代码，暂时让某段代码失效

	# 打印出本次测试的测试结果	
	print('本次测试功能点5个')
	print('测试用例20个')
	print('共执行测试用例20个')
	print('共发现缺陷0个')
	print('用例通过率100%')


##（二）数字和计算
新建名为report\_with\_math.py
	
	print('本次测试覆盖了3个模块')
	print('测试用例总数为: ', 30 + 40 + 30)
	print('执行的测试用例总数为: ', 30 + 40 + 30)
	print('用例最多的模块是B模块，B模块比A模块多出的用例数为', 40 - 30)
	print('A模块执行成功27个用例，执行失败的用例数为', 30 - 27)
	print('B模块的用例全部执行通过， 通过率为百分之', (40 / 40) * 100)
	print('C模块的用例全部执行通过， 通过率为百分之', (30 / 30) * 100)
	print('B模块的用例比C模块多吗?', 40 > 30)
	print('A模块的用例比C模块多吗?', 30 > 30)
	print('B模块的用例比C模块少吗?', 40 < 30)

	# 结束打印
	print('回归不通过')

##（三）变量和名称

新建名为report\_with\_var.py，内容如下

	module_count = 3

	case__a = 30.0
	success_case__a = 27

	case__b = 40.0
	success_case__b = 40

	case__c = 30.0
	success_case__c = 30

	print('本次测试覆盖了',module_count ,'个模块')
	print('测试用例总数为: ', case__a + case__b + case__c)
	print('执行的测试用例总数为: ', case__a + case__b + case__c)
	print('用例最多的模块是B模块，B模块比A模块多出的用例数为', case__b - case__a)
	print('A模块执行成功', success_case__a)
	print('个用例，执行失败的用例数为', case__a - success_case__a)
	print('A模块用例通过率为百分之', success_case__a / case__a * 100)
	print('B模块的用例全部执行通过， 通过率为百分之', (success_case__b / case__b) * 100)
	print('C模块的用例全部执行通过， 通过率为百分之', (success_case__b / case__b) * 100)
	print('B模块的用例比C模块多吗?', case__b > case__c)
	print('A模块的用例比C模块多吗?', case__a > case__c)
	print('B模块的用例比C模块少吗?', case__b < case__c)

	# 结束打印
	print('回归不通过')


##（四）字符串和文本
在python里，字符串往往表现为用单引号''或者是双引号""包裹起来的一些文字

s1 = '本次测试覆盖了100个模块'

s2 = "本次测试运行了100个用例"

f-string：可以方便的在字符串中包含变量

module_count = 3
f"本次测试覆盖了{module_count}个模块"，支持format语法

新建名为report\_with\_f\_string.py
	
	module_count = 3

	case_a = 30.0
	success_case_a = 27

	case_b = 40.0
	success_case_b = 40

	case_c = 30.0
	success_case_c = 30

	print(f"本次测试覆盖了{module_count}个模块")
	print(f"测试用例总数为: {case_a + case_b + case_c}")
	print(f"执行的测试用例总数为: {case_a + case_b + case_c}")
	print(f"用例最多的模块是B模块，B模块比A模块多出的用例数为: {case_b - case_a}")
	print(f'A模块执行成功{success_case_a}个用例')
	print(f'执行失败的用例数为{case_a - success_case_a}')
	print('A模块用例通过率为百分之{}'.format(success_case_a / case_a * 100))
	print('B模块的用例全部执行通过， 通过率为百分之{}'.format((success_case_b / case_b) * 100))
	print('C模块的用例全部执行通过， 通过率为百分之{}'.format((success_case_b / case_b) * 100))

	test_type = '回归测试'
	test_result = '不通过'

	# 结束打印
	print(test_type + test_result)

##（五）转义序列和多行文本

特殊的字符组合我们可以称之为转义序列

* \n: 换行
* \t: tab，可以当成是缩进
* \: 反斜杠
* \’: 单引号，可以在单引号字符串中打印出单引号
* \”: 双引号，可以在双引号字符串中打印出双引号

多行文本

	
	my_str="""
	this is the first line
	this is the second line
	this is the last line
	"""

新建名为print\_test\_case.py


	test_scenario = "登录场景\n"

	test_case_name = "\t正常登录: \n"

	# two tabs
	tt = "\t\t"

	test_step = f"{tt}1.打开chrome浏览器\n{tt}2.输入www.itest.info\n{tt}3.在登录表单中输入用户名:example，密码:example\n{tt}4.登记登录按钮\n"

	test_assert = f"{tt}应该跳转到www.itest.info/login_success页面，并出现\"登录成功\"的提示"

	print(test_scenario + test_case_name + test_step + test_assert)

	test_login_failed = """
			密码错误:
					1.打开chrome浏览器
					2.输入www.itest.info
					3.在登录表单中输入用户名:example，密码:incorrect
					4.登记登录按钮
					页面不发生跳转，并出现\"登录失败\"的提示
	"""
	print(test_login_failed)


##（六）获取用户输入

input()函数来获取用户输入的信息，并保存在变量里。

新建名为gen\_test\_case.py

	case_name = input("请输入用例名称:\n")
	test_data = input("请输入用到的测试数据，比如: 测试站点=www.itest.info:\n")
	test_steps = input("请输入测试步骤:\n")
	test_assert = input("请输入测试断言(预期结果):\n")

	formatter = """
	用例名称: {}
	测试数据: {}
	测试步骤: {}
	测试断言: {}
	"""

	print(formatter.format(case_name, test_data, test_steps, test_assert))



##（七）命令行参数与unpack

argv里保存了脚本运行时你传入的所有的命令行参数以及脚本名称

	python something.py first second third # argv = [something.py, first, second, third]
	python something.py my_var # argv = [something.py, my_var]
	python something.py # argv = [something.py]

unpack就是把一组数据按顺序的保存到变量里

	argv = ['something.py', 'first', 'second', 'third']
	a, b, c, d = argv # a='something.py' b='first', c=second d='third'
	argv = ['something.py', 'my_var']
	script, the_var = argv # script='something.py' the_var='my_var'

---
修改gen\_test\_case.py

	#import关键字就可以把我们需要的内容导入进来，从而在脚本里使用。
	from sys import argv

	script, case_id = argv
	print(f"创建测试用例\n用例编号: {case_id}")
	case_name = input("请输入用例名称:\n")
	test_data = input("请输入用到的测试数据，比如: 测试站点=www.itest.info:\n")
	test_steps = input("请输入测试步骤:\n")
	test_assert = input("请输入测试断言(预期结果):\n")

	formatter = """
	用例编号: {}
	用例名称: {}
	测试数据: {}
	测试步骤: {}
	测试断言: {}
	"""

	print(formatter.format(case_id, case_name, test_data, test_steps, test_assert))


##（八）读取文件

新建名为read\_case.py

	from sys import argv

	script, file_path = argv

	print(f"读取文件: {file_path}")
	print()
	file_obj = open(file_path)
	print(file_obj.read())
	file_obj.close()

新建名为case001.txt的文本文件

	用例编号: itest001
	用例名称: 登录成功
	测试数据: 用户名:example;密码:example
	测试步骤: 略
	测试断言: 应该可以正确跳转到www.itest.info

运行文件

	$python read_case.py case001.txt

