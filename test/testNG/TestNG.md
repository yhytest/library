##（一）TestNG介绍与安装

TestNG 官方网址：[http://testng.org/doc/](http://testng.org/doc/)

TestNG是一个测试框架的灵感来自JUnit和NUnit,但引入一些新的功能，使它更强大和更容易使用

TestNG 表示下一代(Next Generation的首字母)。

它的设计覆盖所有类别的测试：单元、功能、端到端、集成等。

案例基于IDEA 和 Maven 

	
	<!-- https://mvnrepository.com/artifact/org.testng/testng -->
	<dependency>
		<groupId>org.testng</groupId>
		<artifactId>testng</artifactId>
		<version>6.14.3</version>
		<scope>test</scope>
	</dependency>

##（二）Hello World
创建 FirstTest 测试类

	
	import org.testng.annotations.Test;
	import static org.testng.AssertJUnit.assertEquals;


	public class FirstTest {
		
		//通过 @Test 注解一个方法为测试用例
		@Test
		public void testCase(){
			//通过 assertEquals() 方法来断言两个数是否相等
			assertEquals(2+2, 4);
		}
	}

##（三）TestNG 之 FixTrue
Test Fixture 是指一个测试运行所需的固定环境

![](https://i.imgur.com/ZwjUtES.png)
创建FixtureTest类
	
	import org.testng.annotations.*;


	public class FixtureTest {

		//在当前测试类开始时运行。
		@BeforeClass
		public static void beforeClass(){
			System.out.println("-------------------beforeClass");
		}

		//在当前测试类结束时运行。
		@AfterClass
		public static void afterClass(){
			System.out.println("-------------------afterClass");
		}

		//每个测试方法运行之前运行
		@BeforeMethod
		public void before(){
			System.out.println("=====beforeMethod");
		}

		//每个测试方法运行之后运行
		@AfterMethod
		public void after(){
			System.out.println("=====afterMethod");
		}

		@Test
		public void testCase1(){
			System.out.println("test case 1");
		}

		@Test
		public void testCase2(){
			System.out.println("test case 2");
		}

	}


##（四）testng.xml文件解析
TestNG 与 Junit 比较大的一个差异就是前者通过 testng.xml 文件来配置测试用例的执行

testng.xml文件参数说明

	<!-- 必须要添加，表示遵循的规范文件-->
	<!DOCTYPE suite SYSTEM "http://testng.org/testng-1.0.dtd" >
	<!--suite 表示定义了的一个测试套件-->
	<!--name 定义测试套件的名称。-->
	<!--verbose 定义命令行信息打印等级，可选值(1|2|3|4|5) -->
	<suite name="测试套件" verbose="1" >
		<!--test 表示定义了一个测试 name 定义测试的名称-->
		<test name="简单测试">
			<!--classes 表示定义一组测试类-->
			<classes>
				<!--class 表示定义一个测试类 name 定义了类的路径-->
				<class name="course4.FirstTest"/>
				<class name="course4.SecondTest"/>
			</classes>
		</test>
	</suite>

##（五）测试级别设置

在我们创建测试用例时，大概分三个层级。

* 测试包（目录）
* 测试类（文件）
* 测试用例（@Test 注解的方法）


如何通过 testng.mxl 文件配置控制这三个级别用例的执行。

* 指定运行测试包

		<!DOCTYPE suite SYSTEM "http://testng.org/testng-1.0.dtd" >
		<suite name="测试套件" verbose="1" >
		    <test name="简单测试">
				<!--packages 定义一组测试包-->
		        <packages>
					<!--package 定义一个测试包 name 指定测试包（目录）的名称-->
		            <package name="test.sample" />
		            <package name="test.sample2" />
		        </packages>
		    </test>
		</suite>

* 指定运行测试类

		<!DOCTYPE suite SYSTEM "http://testng.org/testng-1.0.dtd" >
			<!--suite 表示定义了的一个测试套件-->
			<!--name 定义测试套件的名称。-->
			<!--verbose 定义命令行信息打印等级，可选值(1|2|3|4|5) -->
			<suite name="测试套件" verbose="1" >
				<!--test 表示定义了一个测试 name 定义测试的名称-->
				<test name="简单测试">
					<!--classes 表示定义一组测试类-->
					<classes>
						<!--class 表示定义一个测试类 name 定义了类的路径-->
						<class name="course4.FirstTest"/>
						<class name="course4.SecondTest"/>
					</classes>
				</test>
			</suite>


* 指定运行测试用例

		<!DOCTYPE suite SYSTEM "http://testng.org/testng-1.0.dtd" >
		<suite name="测试套件" verbose="1" >
		    <test name="简单测试">
		        <classes>
		            <class name="test.sample.FirstTest">
						<!--methods 定义一组测试方法-->
						<!--methods 必须包含在<class>标签中-->
		                <methods>
							<!--include 指定包含的测试用例（方法）
							name 指定测试用例（方法）的名称-->
		                    <include name="testCase" />
		                </methods>
		            </class>
		        </classes>
		    </test>
		</suite>


##（六）

##（七）

##（八）

##（九）

##（十）