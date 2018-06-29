##（一）基本概念
unittest是python自带的单元测试框架，又被称为”PyUnit”，是python版本的JUint实现。


了解一下unittest库的一些重要概念:

    test fixture:初始化和清理测试数据及环境
    test case是测试用例
    test suite是用例集合
    test runner的作用是运行用例并返回结果

##（二）基本用法
看一下unittest的基本用法

	import unittest

	#继承unittest.TestCase类来定义我们自己的测试用例
	class TestStringMethods(unittest.TestCase):
		
		#测试用例中方法名以test开头的方法才是测试方法
		def test_upper(self):
			self.assertEqual('foo'.upper(), 'FOO')

		def test_isupper(self):
			#assertTrue()和assertFalse来做是非判断
			self.assertTrue('FOO'.isupper())
			self.assertFalse('Foo'.isupper())

		def test_split(self):
			s = 'hello world'
			self.assertEqual(s.split(), ['hello', 'world'])
			# check that s.split fails when the separator is not a string
			# assertRaises()来判断预期的异常是否有被抛出
			with self.assertRaises(TypeError):
				s.split(2)

	if __name__ == '__main__':
		#unittest.main提供了最简单的运行用例的方式
		unittest.main()

##（三）测试弱密码
text fixture的主要功能是初始化测试数据或环境以及清理测试数据或环境。

Test fixture最简单的实现方式是通过自定义下面的2个方法:

TestCase.setUp方法在每个测试方法运行之前都会运行一次，适合为每个用例都初始化一遍数据
TestCase.tearDown方法在每个测试方法运行之后都会运行一次，适合为每个用例都清理一遍数据

新建名为test\_password\_1.py的文本文件

	import unittest
	
	class PasswordTeseCase(unittest.TestCase):
	
	    def setUp(self):
	        print('set up')
	        self.test_data = [
	            dict(name='jack', password='Iloverose'),
	            dict(name='rose', password='Ilovejack'),
	            dict(name='tom', password='password123')
	        ]
	
	    def test_week_password(self):
	        for data in self.test_data:
	            passwd = data['password']
	
	            self.assertTrue(len(passwd) >= 6)
	
	            msg = "user %s has a weak password" %(data['name'])
	            self.assertTrue(passwd != 'password', msg)
	            self.assertTrue(passwd != 'password123', msg)
	
	    def test_dummy(self):
	        pass
	
	if __name__ == '__main__':
	    unittest.main()

##（四）读取测试数据并测试弱密码
通过读取文件的方式，每次动态从测试用例读取数据，这样数据的改变并不会影响用例

新建user_data.json文件，内容如下

	[
	  {"name":"jack","password":"Iloverose"},
	  {"name":"rose","password":"Ilovejack"},
	  {"name":"tom","password":"password123"}
	]


新建test\_password\_2.py，内容如下

	import unittest
	import json

	class PasswordWithJsonTeseCase(unittest.TestCase):
		data_file_path = './user_data.json'

		def setUp(self):
			print('set up')
			self.test_data = json.loads(open(self.data_file_path).read())

		def test_week_password(self):
			# 通过解析json文件的方式来赋值
			for data in self.test_data:
				passwd = data['password']

				self.assertTrue(len(passwd) >= 6)

				msg = "user %s has a weak password" %(data['name'])
				self.assertTrue(passwd != 'password', msg)
				self.assertTrue(passwd != 'password123', msg)

		def test_dummy(self):
			pass

	if __name__ == '__main__':
		unittest.main()

重构代码

新建文件`test\_password\_3.py

	import unittest
	import json

	class WeakPasswordTeseCase(unittest.TestCase):

		@classmethod
		#tearDownClass: 在所有测试方法执行完之后被调用1次
		#setUpClass方法在每个测试用例类执行之前会执行一次
		def setUpClass(kls):
			data_file_path = './user_data.json'
			print('before all test methods')
			# 使用open 方法的with模式可以在读取文件后自动关闭文件
			with open(data_file_path) as f:
				kls.test_data = json.loads(f.read())

		def test_week_password(self):
			for data in self.test_data:
				passwd = data['password']

				self.assertTrue(len(passwd) >= 6)

				msg = "user %s has a weak password" %(data['name'])
				self.assertTrue(passwd != 'password', msg)
				self.assertTrue(passwd != 'password123', msg)

		def test_dummy(self):
			pass

	if __name__ == '__main__':
		unittest.main()


##（五）找出所有是弱密码的用户
当我们的测试数据是下面这些的时候，我们的用例是有问题的

	[
	  {"name":"jack","password":"Iloverose"},
	  {"name":"rose","password":"Ilovejack"},
	  {"name":"tom","password":"password123"},
	  {"name":"jerry","password":"password"}
	]
只能找出tom是弱密码的用户，jerry这个用户会成为漏网之鱼
	
在unittest中，一旦某个测试方法中的断言失败，后续的断言都不会被执行

重构一下我们的用例，让整个用例只断言1次

修改user_data.json文件

	[
	  {"name":"jack","password":"Iloverose"},
	  {"name":"rose","password":"Ilovejack"},
	  {"name":"tom","password":"password123"},
	  {"name":"jerry","password":"password"},
	  {"name":"fred","password":"123456"},
	  {"name":"elma","password":"654321"}
	]
新建test\_password\_4.py文件，内容如下

	import unittest
	import json
	
	class WeakPasswordTeseCase1(unittest.TestCase):
	
	    @classmethod
	    def setUpClass(kls):
	        data_file_path = './user_data.json'
	        print('before all test methods')
	        with open(data_file_path) as f:
	            kls.test_data = json.loads(f.read())
	
	    def test_week_password(self):
	        res = True
	        msg = []
	        for data in self.test_data:
	            passwd = data['password']
	            tmp_res = True
	
	            tmp_res = tmp_res and (len(passwd) >= 6)
	            tmp_res = tmp_res and (passwd != 'password')
	            tmp_res = tmp_res and (passwd != 'password123')
	            if not tmp_res:
	                msg.append("user %s has a weak 
						password %s" %(data['name'], data['password']))
	            res = res and tmp_res
	
	        self.assertTrue(res, "\n".join(msg))
	
	    def test_dummy(self):
	        pass
	
	if __name__ == '__main__':
	    unittest.main()



##（六）命令行接口
unittest支持命令行接口，我们可以在命令行里指定运行具体的测试用例。

在test\_password\_1.py中定义了PasswordTeseCase用例

我们可以从命令行中指定只运行该用例。

    $ python -m unittest test_password_1.PasswordTeseCase

还可以使用-v参数来获得更详细的输出

    $ python -m unittest test_password_1.PasswordTeseCase -v


##（七）各种断言方法
![](https://i.imgur.com/18EXsXA.png)
![](https://i.imgur.com/UZJdyYK.png)
##（八）断言异常
有时候需要断言一些方法会抛出异常，这些异常需要符合我们的预期。

新建test_exception.py文件

	import unittest

	class DivZeroTestCase(unittest.TestCase):

		def test_should_raise_exception(self):
			# 断言异常是有套路的，使用with语句加assertRaises
			# assertRaises的参数中传入预期的异常
			with self.assertRaises(ZeroDivisionError):
				1 / 0

	if __name__ == '__main__':
		unittest.main()



