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


##（六）TestNG 用例分组
测试用例可以有多个维度去标识

根据用例的重要程度划分：重要程度：低——>中——>高

根据用例的类型划分：类型：正常——>异常

TestNG 允许我们给测试用例贴标签。

	import org.testng.annotations.Test;

	import static org.testng.AssertJUnit.assertEquals;


	@Test(groups = {"功能测试"})
	public class TagTest {

		@Test(groups={"高", "正常"})
		public void testCase1(){
			assertEquals(2+2, 4);
		}

		@Test(groups = {"高", "正常"})
		public void testCase2(){
			assertEquals(5-3, 2);
		}
		@Test(groups = {"中", "正常"})
		public void testCase3(){
			assertEquals(2/1, 2);
		}

		@Test(groups = {"低", "异常"})
		public void testCase4(){
			assertEquals(2/0, 1);
		}

	}
	
接下来配置 testng.xml 

	<!DOCTYPE suite SYSTEM "http://testng.org/testng-1.0.dtd" >
	<suite name="测试套件" verbose="1" >
		<test name="简单测试">
		<!--groups 测试组标签-->
			<groups>
				<!--run 运行测试-->
				<run>
					<!--exclude 排除不执行的测试用例 -->
					<exclude name="异常"  />  
					<!--include 指定执行的测试用例 -->
					<include name="高"  />  
				</run>
			</groups>

			<classes>
				<class name="test.sample.TagTest"/>
			</classes>
		</test>
	</suite>
##（七）TestNG 用例执行顺序

希望用例按照我们要求的顺序来执行

	import org.testng.annotations.Test;
	import static org.testng.AssertJUnit.assertEquals;


	public class CaseRunTest {

		@Test
		public void testCase1(){
			assertEquals(2+2, 4);
		}

		@Test
		public void testCase2(){
			assertEquals(2+2, 4);
		}

		@Test
		public void testCase3(){
			assertEquals(2+2, 4);
		}
	}
	
通过 testng.xml 文件修改配置。

	<!DOCTYPE suite SYSTEM "http://testng.org/testng-1.0.dtd" >
	<suite name="测试套件">
		<!--preserve-order 参数用于控制测试用例的执行顺序 默认为true-->
		<!--true，测试用例的排列顺序执行-->
		<!--testCase > testCase1 > testCase2-->
		<!--false，默认会按照用例的名称的有字母/数字的顺序执行-->
		<!--testCase1 > testCase2 > testCase3-->
		<test name="简单测试" preserve-order="false">
			<classes>
				<class name="test.sample.CaseRunTest">
					<methods>
						<include name="testCase3" />
						<include name="testCase1" />
						<include name="testCase2" />
					</methods>
				</class>
			</classes>
		</test>
	</suite>	

##（八）TestNG 用例依赖

当某一条用例运行失败时，其它用例必然也会失败.可以设置用例之间的依赖。

测试方法依赖

	import org.testng.annotations.Test;
	import static org.testng.AssertJUnit.assertEquals;


	public class DependentMethodsTest {

		@Test
		public void testAdd1(){
			assertEquals(3+1, 5);
		}
		
		//dependsOnMethods 来设置用例的依赖
		//当 testAdd1() 运行失败时，则 testAdd2() 不再被执行
		@Test(dependsOnMethods = {"testAdd1"})
		public void testAdd2(){
			assertEquals(3+2, 5);
		}

	}


测试组依赖

	import org.testng.annotations.Test;
	import static org.testng.AssertJUnit.assertEquals;


	public class DependentGroupsTest {

		@Test(groups={"funtest"})
		public void testAdd1(){
			assertEquals(3+1, 5);
		}

		@Test(groups={"funtest"})
		public void testAdd2(){
			assertEquals(3+2, 5);
		}
		
		//dependsOnGroups 来设置组的依赖
		//testAdd1/2/3同属于于 funtest组
		//当有一条用例运行失败，则testAdd3() 不再执行
		@Test(dependsOnGroups = {"funtest"})
		public void testAdd3(){
			assertEquals(3+2, 5);
		}

	}


##（九）TestNG 用例参数化


增加用例的可配置性和减少相同用例的编写。

通过 @Parameters 实现参数化

	import org.testng.annotations.Parameters;
	import org.testng.annotations.Test;
	import static org.testng.AssertJUnit.assertEquals;
	
	public class DataProviderTest {
	
	    @Test
		//@Parameters 获取参数化数据,作为 testAdd1() 测试方法的参数
	    @Parameters({"add1","add2","result"})
	    public void testAdd1(int add1, int add2, int result){
	        assertEquals(add1+ add2, result);
	    }
	
	}


具体的测试数据在 testng.mxl 文件中设置。

	<!DOCTYPE suite SYSTEM "http://testng.org/testng-1.0.dtd" >
	<suite name="测试套件">
		<test name="简单测试">
			<!--parameter 定义测试数据 name 参数名 value 参数值-->
			<parameter name="add1" value="3"/>
			<parameter name="add2" value="2"/>
			<parameter name="result" value="5"/>
			<classes>
				<class name="test.sample.DataProviderTest" />
			</classes>
		</test>
	</suite>

通过 @DataProvider 实现参数化

	import org.testng.annotations.DataProvider;
	import org.testng.annotations.Test;
	import static org.testng.AssertJUnit.assertEquals;

	public class DataProviderTest {

		// 定义对象数组
		@DataProvider(name = "add")
		public Object[][] Users() {
			return new Object[][] {
					{ 3, 2, 5 },
					{ 2, 2, 4 },
					{ 3, 3, 7 },
			};
		}
		
		//调用定义的对象数组，并通过参数获取相应的测试数据
		@Test(dataProvider="add")		
		public void testAdd2(int add1, int add2, int result){
			assertEquals(add1+add2, result);
		}

	}

##（十）TestNG 多线程运行用例

TestNG 是支持多程技术的单元测试框架。适用于UI自动化测试

多线程配置testng.xml文件

	<!DOCTYPE suite SYSTEM "http://testng.org/testng-1.0.dtd" >
	<!--parallel 设置多线程的级别划分-->
	<!--parallel=“methods”: TestNG将在不同的线程中运行所有的测试方法-->
	<!--parallel=“tests”: TestNG 将在同一个线程中运行相同的标记的所有方法-->
	<!--parallel=“classes”: TestNG将在同一个线程中运行同一个类中的所有方法-->
	<!--parallel=“instances”: TestNG将在同一个线程中运行相同实例中的所有方法-->
	<!--thread-count 用于指定线程的个数-->
	<suite name="测试套件" parallel="classes" thread-count="2" >
		<test name="简单测试">
			<classes>
				<class name="test.sample.FirstTest" />
				<class name="test.sample.SecondTest" />
			</classes>
		</test>
	</suite>


##（十一） TestNG 多线程运行用例
菜单栏： “Run” –>“Edit Configuraction…

![](https://i.imgur.com/mLId32A.png)

选择运行测试用例的 testng.xml 文件–>“Configuration”–>“Listeners”–>

勾选“Use default reporters” 选项， 最后点击“OK” 按钮， 完成设置

##（十二） TestNG 其他使用技巧

	import org.testng.annotations.Test;
	import static org.testng.AssertJUnit.assertEquals;

	public class OtherTest {

		//enabled 设置用例是否跳过执行
		//默认为true不跳过。false跳过执行
		@Test(enabled = false)
		public void testCase1(){
			assertEquals(2+2, 4);
		}

		// timeOut 设置用例运行的超时间
		@Test(timeOut = 3000)
		public void testCase2() throws InterruptedException {
			Thread.sleep(3001);
		}

		// expectedExceptions 用来预设用例运行会出现的异常
		@Test(expectedExceptions = RuntimeException.class)
		public void testCase3(){
			assertEquals(2/0,1);
		}

	}

