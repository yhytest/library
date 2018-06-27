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

新建名为test_password_1.py的文本文件

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

##（五）

##（六）

##（七）

##（八）

##（九）

##（十）