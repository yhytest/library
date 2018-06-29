1、面向对象的特征有哪些方面
(1).抽象：
抽象就是忽略一个主题中与当前目标无关的那些方面，以便更充分地注意与当前目标有关的方面。抽象并不打算了解全部问题，而只是选择其中的一部分，暂时不用部分细节。抽象包括两个方面，一是过程抽象，二是数据抽象。
(2).继承：
继承是一种联结类的层次模型，并且允许和鼓励类的重用，它提供了一种明确表述共性的方法。对象的一个新类可以从现有的类中派生，这个过程称为类继承。新类继承了原始类的特性，新类称为原始类的派生类（子类），而原始类称为新类的基类（父类）。派生类可以从它的基类那里继承方法和实例变量，并且类可以修改或增加新的方法使之更适合特殊的需要。
(3).封装：
封装是把过程和数据包围起来，对数据的访问只能通过已定义的界面。面向对象计算始于这个基本概念，即现实世界可以被描绘成一系列完全自治、封装的对象，这些对象通过一个受保护的接口访问其他对象。
(4). 多态性：
多态性是指允许不同类的对象对同一消息作出响应。多态性包括参数化多态性和包含多态性。多态性语言具有灵活、抽象、行为共享、代码共享的优势，很好的解决了应用程序函数同名问题。
2、String是最基本的数据类型吗? 
基本数据类型包括byte、int、char、long、float、double、boolean和short。
java.lang.String类是final类型的，因此不可以继承这个类、不能修改这个类。为了提高效率节省空间，我们应该用StringBuffer类
3、int 和 Integer 有什么区别
Java 
提供两种不同的类型：引用类型和原始类型（或内置类型）。Int是java的原始数据类型，Integer是java为int提供的封装类。Java为每个原始类型提供了封装类。
原始类型封装类
booleanBoolean 
charCharacter 
byteByte 
shortShort 
intInteger 
longLong 
floatFloat 
doubleDouble 
引用类型和原始类型的行为完全不同，并且它们具有不同的语义。引用类型和原始类型具有不同的特征和用法，它们包括：大小和速度问题，这种类型以哪种类型的数据结构存储，当引用类型和原始类型用作某个类的实例数据时所指定的缺省值。对象引用实例变量的缺省值为
null，而原始类型实例变量的缺省值与它们的类型有关。
4、String 和StringBuffer的区别
JAVA平台提供了两个类：String和StringBuffer，它们可以储存和操作字符串，即包含多个字符的字符数据。这个String类提供了数值不可改变的字符串。而这个StringBuffer类提供的字符串进行修改。当你知道字符数据要改变的时候你就可以使用StringBuffer。典型地，你可以使用StringBuffers来动态构造字符数据。
5、运行时异常与一般异常有何异同？
异常表示程序运行过程中可能出现的非正常状态，运行时异常表示虚拟机的通常操作中可能遇到的异常，是一种常见运行错误。java编译器要求方法必须声明抛出可能发生的非运行时异常，但是并不要求必须声明抛出未被捕获的运行时异常。
6、说出Servlet的生命周期，并说出Servlet和CGI的区别。
Servlet被服务器实例化后，容器运行其init方法，请求到达时运行其service方法，service方法自动派遣运行与请求对应的doXXX方法（ doGet，doPost）等，当服务器决定将实例销毁的时候调用其destroy方法。
与cgi的区别在于servlet处于服务器进程中，它通过多线程方式运行其service方法，一个实例可以服务于多个请求，并且其实例一般不会销毁，而CG I对每个请求都产生新的进程，服务完成后就销毁，所以效率上低于servlet。
7、说出ArrayList,Vector, LinkedList的存储性能和特性
ArrayList 
和Vector都是使用数组方式存储数据，此数组元素数大于实际存储的数据以便增加和插入元素，它们都允许直接按序号索引元素，但是插入元素要涉及数组元素移动等内存操作，所以索引数据快而插入数据慢，Vector由于使用了synchronized方法（线程安全），通常性能上较ArrayList差，而 Linke dList使用双向链表实现存储，按序号索引数据需要进行前向或后向遍历，但是插入数据时只需要记录本项的前后项即可，所以插入速度较快。
9、Collection 和 Collections的区别
Collection是集合类的上级接口，继承与他的接口主要有Set 
和List. 
Collections是针对集合类的一个帮助类，他提供一系列静态方法实现对各种集合的搜索、排序、线程安全化等操作。
10、&和&&的区别。
&是位运算符，表示按位与运算，&&是逻辑运算符，表示逻辑与（and）。
11、HashMap和Hashtable的区别。
HashMap是Hashtable的轻量级实现（非线程安全的实现），他们都完成了Map接口，主要区别在于HashMap允许空（null）键值（key） ,由于非线程安全，效率上可能高于Hashtable。
HashMap允许将null作为一个entry的key或者value，而Hashtable不允许。
HashMap把Hashtable的contains方法去掉了，改成containsvalue和containsKey。因为contains方法容易让人引起误解。
Hashtable继承自Dictionary类，而HashMap是Java1.2引进的Map 
interface的一个实现。
最大的不同是，Hashtable的方法是Synchronize的，而HashMap不是，在多个线程访问Hashtable时，不需要自己为它的方法实现同步，而HashMap 
就必须为之提供外同步。
Hashtable和HashMap采用的hash/rehash算法都大概一样，所以性能不会有很大的差异。
12、final, finally, finalize的区别。
final 
用于声明属性，方法和类，分别表示属性不可变，方法不可覆盖，类不可继承。
finally是异常处理语句结构的一部分，表示总是执行。
finalize是Object类的一个方法，在垃圾收集器执行的时候会调用被回收对象的此方法，可以覆盖此方法提供垃圾收集时的其他资源回收，例如关闭文件等。
13、sleep() 和 wait() 有什么区别? 
sleep是线程类（Thread）的方法，导致此线程暂停执行指定时间，给执行机会给其他线程，但是监控状态依然保持，到时后会自动恢复。调用sleep不会释放对象锁。
wait是Object类的方法，对此对象调用wait方法导致本线程放弃对象锁，进入等待此对象的等待锁定池，只有针对此对象发出notify方法（或not ifyAll）后本线程才进入对象锁定池准备获得对象锁进入运行状态。
14、Overload和Override的区别。Overloaded的方法是否可以改变返回值的类型? 
方法的重写Overriding和重载Overloading是Java多态性的不同表现。重写Overriding是父类与子类之间多态性的一种表现，重载O verloading是一个类中多态性的一种表现。如果在子类中定义某方法与其父类有相同的名称和参数，我们说该方法被重写
(Overriding)。子类的对象使用这个方法时，将调用子类中的定义，对它而言，父类中的定义如同被”屏蔽”了。如果在一个类中定义了多个同名的方法，它们或有不同的参数个数或有不同的参数类型，则称为方法的重载(Overloading)。Overloaded的方法是可以改变返回值的类型。
15、error和exception有什么区别? 
error 
表示恢复不是不可能但很困难的情况下的一种严重问题。比如说内存溢出。不可能指望程序能处理这样的情况。
exception 
表示一种设计或实现问题。也就是说，它表示如果程序运行正常，从不会发生的情况。


16、同步和异步有何异同，在什么情况下分别使用他们？举例说明。
如果数据将在线程间共享。例如正在写的数据以后可能被另一个线程读到，或者正在读的数据可能已经被另一个线程写过了，那么这些数据就是共享数据，必须进行同步存取。
当应用程序在对象上调用了一个需要花费很长时间来执行的方法，并且不希望让程序等待方法的返回时，就应该使用异步编程，在很多情况下采用异步途径往往更有效率。


17、abstract class和interface有什么区别? 
声明方法的存在而不去实现它的类被叫做抽象类（abstract 
class），它用于要创建一个体现某些基本行为的类，并为该类声明方法，但不能在该类中实现该类的情况。不能创建abstract 
类的实例。然而可以创建一个变量，其类型是一个抽象类，并让它指向具体子类的一个实例。不能有抽象构造函数或抽象静态方法。Abstract 
类的子类为它们父类中的所有抽象方法提供实现，否则它们也是抽象类为。取而代之，在子类中实现该方法。知道其行为的其它类可以在类中实现这些方法。
接口（interface）是抽象类的变体。在接口中，所有方法都是抽象的。多继承性可通过实现这样的接口而获得。接口中的所有方法都是抽象的，没有一个有程序体。接口只可以定义static 
final成员变量。接口的实现与子类相似，除了该实现类不能从接口定义中继承行为。当类实现特殊接口时，它定义（即将程序体给予）所有这种接口的方法。然后，它可以在实现了该接口的类的任何对象上调用接口的方法。由于有抽象类，它允许使用接口名作为引用变量的类型。通常的动态联编将生效。引用可以转换到接口类型或从接口类型转换，instanceof 
运算符可以用来决定某对象的类是否实现了接口。
18、heap和stack有什么区别。
栈是一种线形集合，其添加和删除元素的操作应在同一段完成。栈按照后进先出的方式进行处理。
堆是栈的一个组成元素
19、forward 和redirect的区别
forward是服务器请求资源，服务器直接访问目标地址的URL，把那个URL的响应内容读取过来，然后把这些内容再发给浏览器，浏览器根本不知道服务器发送的内容是从哪儿来的，所以它的地址栏中还是原来的地址。
redirect就是服务端根据逻辑,发送一个状态码,告诉浏览器重新去请求那个地址，一般来说浏览器会用刚才请求的所有参数重新请求，所以session,r equest参数都可以获取。
21、Static Nested Class 和 Inner Class的不同。
Static Nested 
Class是被声明为静态（static）的内部类，它可以不依赖于外部类实例被实例化。而通常的内部类需要在外部类实例化后才能实例化。
23、什么时候用assert。
assertion(断言)在软件开发中是一种常用的调试方式，很多开发语言中都支持这种机制。在实现中，assertion就是在程序中的一条语句，它对一个 boolean表达式进行检查，一个正确程序必须保证这个boolean表达式的值为true；如果该值为false，说明程序已经处于不正确的状态下，系统将给出警告或退出。一般来说，assertion用于保证程序最基本、关键的正确性。assertion检查通常在开发和测试时开启。为了提高性能，在软件发布后，assertion检查通常是关闭的。
24、GC是什么? 为什么要有GC? 
GC是垃圾收集的意思（Gabage 
Collection）,内存处理是编程人员容易出现问题的地方，忘记或者错误的内存回收会导致程序或系统的不稳定甚至崩溃，Java提供的GC功能可以自动监测对象是否超过作用域从而达到自动回收内存的目的，Java语言没有提供释放已分配内存的显示操作方法。


25、short s1 = 1; s1 = s1 + 1;有什么错? short s1 = 1; s1 += 
1;有什么错? 
short s1 = 1; s1 = s1 + 1; 
（s1+1运算结果是int型，需要强制转换类型）
short s1 = 1; s1 += 1;（可以正确编译）


26、Math.round(11.5)等於多少? Math.round(-11.5)等於多少? 
Math.round(11.5)==12 
Math.round(-11.5)==-11 
round方法返回与参数最接近的长整数，参数加1/2后求其floor. 


27、String s = new String(“xyz”);创建了几个String Object? 
两个


28、设计4个线程，其中两个线程每次对j增加1，另外两个线程对j每次减少1。写出程序。
以下程序使用内部类实现线程，对j增减的时候没有考虑顺序问题。
public class ThreadTest1{ 
private int j; 
public static void main(String args[]){ 
ThreadTest1 tt=new ThreadTest1(); 
Inc inc=tt.new Inc(); 
Dec dec=tt.new Dec(); 
for(int i=0;i29、Java有没有goto?[/color] 
java中的保留字，现在没有在java中使用。

30、启动一个线程是用run()还是start()? 
启动一个线程是调用start()方法，使线程所代表的虚拟处理机处于可运行状态，这意味着它可以由JVM调度并执行。这并不意味着线程就会立即运行。run( )方法可以产生必须退出的标志来停止一个线程。

33、给我一个你最常见到的runtime exception。
ArithmeticException, ArrayStoreException, BufferOverflowException, 
BufferUnderflowException, CannotRedoException, CannotUndoException, 
ClassCastException, CMMException, ConcurrentModificationException, 
DOMException, EmptyStackException, IllegalArgumentException, 
IllegalMonitorStateException, IllegalPathStateException, 
IllegalStateException, ImagingOpException, IndexOutOfBoundsException, 
MissingResourceException, NegativeArraySizeException, 
NoSuchElementException, NullPointerException, ProfileDataException, 
ProviderException, RasterFormatException, SecurityException, 
SystemException, UndeclaredThrowableException, 
UnmodifiableSetException, UnsupportedOperationException 


34、接口是否可继承接口? 
抽象类是否可实现(implements)接口? 
抽象类是否可继承实体类(concrete class)? 
接口可以继承接口。抽象类可以实现(implements)接口，抽象类是否可继承实体类，但前提是实体类必须有明确的构造函数。


35、List, Set, Map是否继承自Collection接口? 
List，Set是，Map不是


36、说出数据连接池的工作机制是什么? 
J2EE 
服务器启动时会建立一定数量的池连接，并一直维持不少于此数目的池连接。客户端程序需要连接时，池驱动程序会返回一个未使用的池连接并将其表记为忙。如果当前没有空闲连接，池驱动程序就新建一定数量的连接，新建连接的数量有配置参数决定。当使用的池连接调用完成后，池驱动程序将此连接表记为空闲，其他调用就可以使用这个连接。
37、abstract的method是否可同时是static,是否可同时是native，是否可同时是synchronized? 
都不能
38、数组有没有length()这个方法? 
String有没有length()这个方法？
数组没有length()这个方法，有length的属性。String有有length()这个方法。
39、Set里的元素是不能重复的，那么用什么方法来区分重复与否呢? 
是用==还是equals()? 它们有何区别? 
Set里的元素是不能重复的，那么用iterator()方法来区分重复与否。equals()是判读两个Set是否相等。
equals()和==方法决定引用值是否指向同一对象equals()在类中被覆盖，为的是当两个分离的对象的内容和类型相配的话，返回真值。
40、构造器Constructor是否可被override? 
构造器Constructor不能被继承，因此不能重写Overriding，但可以被重载Overloading。
41、是否可以继承String类? 
String类是final类故不可以继承。
42、swtich是否能作用在byte上，是否能作用在long上，是否能作用在String上? 
switch（expr1）中，expr1是一个整数表达式。因此传递给
switch 和 case 语句的参数应该是 int、 short、 char 或者
byte。long,string 都不能作用于swtich。
43、try 
{}里有一个return语句，那么紧跟在这个try后的finally 
{}里的code会不会被执行，什么时候被执行，在return前还是后? 
会执行，在return前执行。


45、两个对象值相同(x.equals(y) == true)，但却可有不同的hash code，这句话对不对? 
不对，有相同的hash code。
46、当一个对象被当作参数传递到一个方法后，此方法可改变这个对象的属性，并可返回变化后的结果，那么这里到底是值传递还是引用传递? 
是值传递。Java 
编程语言只有值传递参数。当一个对象实例作为一个参数被传递到方法中时，参数的值就是对该对象的引用。对象的内容可以在被调用的方法中改变，但对象的引用是永远不会改变的。
47、当一个线程进入一个对象的一个synchronized方法后，其它线程是否可进入此对象的其它方法? 
不能，一个对象的一个synchronized方法只能由一个线程访问。
48、编程题: 写一个Singleton出来。
Singleton模式主要作用是保证在Java应用程序中，一个类Class只有一个实例存在。
一般Singleton模式通常有几种种形式: 
第一种形式: 
定义一个类，它的构造函数为private的，它有一个static的private的该类变量，在类初始化时实例话，通过一个public的getInsta nce方法获取对它的引用,继而调用其中的方法。
public class Singleton { 
private Singleton(){} 

//在自己内部定义自己一个实例，是不是很奇怪？
//注意这是private 只供内部调用
private static Singleton instance = new Singleton(); 

//这里提供了一个供外部访问本class的静态方法，可以直接访问
public static Singleton getInstance() { 
return instance; 
} 

} 
第二种形式: 
public class Singleton { 
private static Singleton instance = null; 
public static synchronized Singleton getInstance() { 
//这个方法比上面有所改进，不用每次都进行生成对象，只是第一次

//使用时生成实例，提高了效率！
if (instance==null) 
instance＝new Singleton(); 
return instance;   } 

} 
其他形式: 
定义一个类，它的构造函数为private的，所有方法为static的。
一般认为第一种形式要更加安全些
49、Java的接口和C++的虚类的相同和不同处。
由于Java不支持多继承，而有可能某个类或对象要使用分别在几个类或对象里面的方法或属性，现有的单继承机制就不能满足要求。与继承相比，接口有更高的灵活性，因为接口中没有任何实现代码。当一个类实现了接口以后，该类要实现接口里面所有的方法和属性，并且接口里面的属性在默认状态下面都是public 
static,所有方法默认情况下是public.一个类可以实现多个接口。
50、Java中的异常处理机制的简单原理和应用。
当JAVA 
程序违反了JAVA的语义规则时，JAVA虚拟机就会将发生的错误表示为一个异常。违反语义规则包括2种情况。一种是JAVA类库内置的语义检查。例如数组下标越界,会引发IndexOutOfBoundsException;访问null的对象时会引发NullPointerException。另一种情况就是JA VA允许程序员扩展这种语义检查，程序员可以创建自己的异常，并自由选择在何时用throw关键字引发异常。所有的异常都是
java.lang.Thowable的子类。


51、垃圾回收的优点和原理。并考虑2种回收机制。
Java语言中一个显著的特点就是引入了垃圾回收机制，使c++程序员最头疼的内存管理的问题迎刃而解，它使得Java程序员在编写程序的时候不再需要考虑内存管理。由于有个垃圾回收机制，
Java中的对象不再有”作用域”的概念，只有对象的引用才有”作用域”。垃圾回收可以有效的防止内存泄露，有效的使用可以使用的内存。垃圾回收器通常是作为一个单独的低级别的线程运行，不可预知的情况下对内存堆中已经死亡的或者长时间没有使用的对象进行清楚和回收，程序员不能实时的调用垃圾回收器对某个对象或所有对象进行垃圾回收。回收机制有分代复制垃圾回收和标记垃圾回收，增量垃圾回收。


52、请说出你所知道的线程同步的方法。
wait():使一个线程处于等待状态，并且释放所持有的对象的lock。
sleep():使一个正在运行的线程处于睡眠状态，是一个静态方法，调用此方法要捕捉InterruptedException异常。
notify():唤醒一个处于等待状态的线程，注意的是在调用此方法的时候，并不能确切的唤醒某一个等待状态的线程，而是由JVM确定唤醒哪个线程，而且不是按优先级。
Allnotity():唤醒所有处入等待状态的线程，注意并不是给所有唤醒线程一个对象的锁，而是让它们竞争。
53、你所知道的集合类都有哪些？主要方法？
最常用的集合类是 List 和 Map。 List 的具体实现包括
ArrayList 和
Vector，它们是可变大小的列表，比较适合构建、存储和操作任何类型对象的元素列表。
List 适用于按数值索引访问元素的情形。
Map 提供了一个更通用的元素存储方法。 Map 
集合类用于存储元素对（称作”键”和”值”），其中每个键映射到一个值。


54、描述一下JVM加载class文件的原理机制? 
JVM中类的装载是由ClassLoader和它的子类来实现的,Java 
ClassLoader 
是一个重要的Java运行时系统组件。它负责在运行时查找和装入类文件的类。


55、char型变量中能不能存贮一个中文汉字?为什么? 
能够定义成为一个中文的，因为java中以unicode编码，一个char占16个字节，所以放一个中文是没问题的


56、多线程有几种实现方法,都是什么?同步有几种实现方法,都是什么? 
多线程有两种实现方法，分别是继承Thread类与实现Runnable接口
同步的实现方面有两种，分别是synchronized,wait与notify 


57、JSP的内置对象及方法。
request表示HttpServletRequest对象。它包含了有关浏览器请求的信息，并且提供了几个用于获取cookie, 
header, 和session数据的有用的方法。
response表示HttpServletResponse对象，并提供了几个用于设置送回
浏览器的响应的方法（如cookies,头信息等）
out对象是javax.jsp.JspWriter的一个实例，并提供了几个方法使你能用于向浏览器回送输出结果。
pageContext表示一个javax.servlet.jsp.PageContext对象。它是用于方便存取各种范围的名字空间、servlet相关的对象的API，并且包装了通用的servlet相关功能的方法。
session表示一个请求的javax.servlet.http.HttpSession对象。Session可以存贮用户的状态信息
applicaton 
表示一个javax.servle.ServletContext对象。这有助于查找有关servlet引擎和servlet环境的信息
config表示一个javax.servlet.ServletConfig对象。该对象用于存取servlet实例的初始化参数。
page表示从该页面产生的一个servlet实例


58、线程的基本概念、线程的基本状态以及状态之间的关系
线程指在程序执行过程中，能够执行程序代码的一个执行单位，每个程序至少都有一个线程，也就是程序本身。
Java中的线程有四种状态分别是：运行、就绪、挂起、结束。


59、JSP的常用指令
isErrorPage(是否能使用Exception对象)，isELIgnored(是否忽略表达式) 
http://……[/size][/url]“%> 

61、servlet的生命周期
web容器加载servlet，生命周期开始。通过调用servlet的init()方法进行servlet的初始化。通过调用 service()方法实现，根据请求的不同调用不同的do***()方法。结束服务，web容器调用servlet的destroy()方法。


63、页面间对象传递的方法
request，session，application，cookie等


64、JSP和Servlet有哪些相同点和不同点，他们之间的联系是什么？
JSP 
是Servlet技术的扩展，本质上是Servlet的简易方式，更强调应用的外表表达。JSP编译后是”类servlet”。Servlet和 JSP最主要的不同点在于，Servlet的应用逻辑是在Java文件中，并且完全从表示层中的HTML里分离开来。而JSP的情况是Java和HTML可以组合成一个扩展名为.jsp的文件。JSP侧重于视图，Servlet主要用于控制逻辑。


65、四种会话跟踪技术
会话作用域ServletsJSP 页面描述
page否是代表与一个页面相关的对象和属性。一个页面由一个编译好的
Java servlet 类（可以带有任何的 include 指令，但是没有
include 动作）表示。这既包括 servlet 又包括被编译成
servlet 的 JSP 页面
request是是代表与 Web 
客户机发出的一个请求相关的对象和属性。一个请求可能跨越多个页面，涉及多个
Web 组件（由于 forward 指令和 include 动作的关系）
session是是代表与用于某个 Web 
客户机的一个用户体验相关的对象和属性。一个 Web 
会话可以也经常会跨越多个客户机请求
application是是代表与整个 Web 
应用程序相关的对象和属性。这实质上是跨越整个 Web 
应用程序，包括多个页面、请求和会话的一个全局作用域


66、Request对象的主要方法：
setAttribute(String 
name,Object)：设置名字为name的request的参数值
getAttribute(String name)：返回由name指定的属性值
getAttributeNames()：返回request对象所有属性的名字集合，结果是一个枚举的实例
getCookies()：返回客户端的所有Cookie对象，结果是一个Cookie数组
getCharacterEncoding()：返回请求中的字符编码方式
getContentLength()：返回请求的Body的长度
getHeader(String name)：获得HTTP协议定义的文件头信息
getHeaders(String name)：返回指定名字的request 
Header的所有值，结果是一个枚举的实例
getHeaderNames()：返回所以request 
Header的名字，结果是一个枚举的实例
getInputStream()：返回请求的输入流，用于获得请求中的数据
getMethod()：获得客户端向服务器端传送数据的方法
getParameter(String 
name)：获得客户端传送给服务器端的有name指定的参数值
getParameterNames()：获得客户端传送给服务器端的所有参数的名字，结果是一个枚举的实例
getParameterValues(String 
name)：获得有name指定的参数的所有值
getProtocol()：获取客户端向服务器端传送数据所依据的协议名称
getQueryString()：获得查询字符串
getRequestURI()：获取发出请求字符串的客户端地址
getRemoteAddr()：获取客户端的IP地址
getRemoteHost()：获取客户端的名字
getSession([Boolean create])：返回和请求相关Session 
getServerName()：获取服务器的名字
getServletPath()：获取客户端所请求的脚本文件的路径
getServerPort()：获取服务器的端口号
removeAttribute(String name)：删除请求中的一个属性


 
68、我们在web应用开发过程中经常遇到输出某种编码的字符，如iso8859-1等，如何输出一个某种编码的字符串？
Public String translate (String str) { 
String tempStr = “”; 
try { 
tempStr = new String(str.getBytes(“ISO-8859-1″), “GBK”); 
tempStr = tempStr.trim(); 

} 
catch (Exception e) { 
System.err.println(e.getMessage()); 

} 
return tempStr; 
} 


 
69、简述逻辑操作(&,|,^)与条件操作(&&,||)的区别。
区别主要答两点：a.条件操作只能操作布尔型的,而逻辑操作不仅可以操作布尔型,而且可以操作数值型
b.逻辑操作不会产生短路


70、XML文档定义有几种形式？它们之间有何本质区别？解析XML文档有哪几种方式？
a: 两种形式 dtd schema，b: 
本质区别:schema本身是xml的，可以被XML解析器解析(这也是从DTD上发展schema的根本目的)，c:有DOM,SAX,STAX等
DOM:处理大型文件时其性能下降的非常厉害。这个问题是由DOM的树结构所造成的，这种结构占用的内存较多，而且DOM必须在解析文件之前把整个文档装入内存 ,适合对XML的随机访问
SAX:不现于DOM,SAX是事件驱动型的XML解析方式。它顺序读取XML文件，不需要一次全部装载整个文件。当遇到像文件开头，文档结束，或者标签开头与标签结束时，它会触发一个事件，用户通过在其回调事件中写入处理代码来处理XML文件，适合对XML的顺序访问
STAX:Streaming API for XML (StAX) 


71、简述synchronized和java.util.concurrent.locks.Lock的异同？
主要相同点：Lock能完成synchronized所实现的所有功能
主要不同点：Lock有比synchronized更精确的线程语义和更好的性能。synchronized会自动释放锁，而Lock一定要求程序员手工释放，并且必须在finally从句中释放。


88、CORBA是什么?用途是什么? 
CORBA 标准是公共对象请求代理结构(Common Object Request 
Broker Architecture)，由对象管理组织 (Object Management 
Group，缩写为
OMG)标准化。它的组成是接口定义语言(IDL), 
语言绑定(binding:也译为联编)和允许应用程序间互操作的协议。其目的为：用不同的程序设计语言书写在不同的进程中运行，为不同的操作系统开发。


91、Servlet执行时一般实现哪几个方法？
public void init(ServletConfig config) 
public ServletConfig getServletConfig() 
public String getServletInfo() 
public void service(ServletRequest request,ServletResponse response) 
public void destroy() 
92、j2ee常用的设计模式？说明工厂模式。
Java中的23种设计模式：
Factory（工厂模式），   Builder（建造模式），   Factory 
Method（工厂方法模式），
Prototype（原始模型模式），Singleton（单例模式），
Facade（门面模式），
Adapter（适配器模式），   Bridge（桥梁模式），
Composite（合成模式），
Decorator（装饰模式），   Flyweight（享元模式），
Proxy（代理模式），
Command（命令模式），   Interpreter（解释器模式），
Visitor（访问者模式），
Iterator（迭代子模式），   Mediator（调停者模式），
Memento（备忘录模式），
Observer（观察者模式），   State（状态模式），
Strategy（策略模式），
Template Method（模板方法模式）， Chain Of 
Responsibleity（责任链模式）
工厂模式：工厂模式是一种经常被使用到的模式，根据工厂模式实现的类可以根据提供的数据生成一组类中某一个类的实例，通常这一组类有一个公共的抽象父类并且实现了相同的方法，但是这些方法针对不同的数据进行了不同的操作。首先需要定义一个基类，该类的子类通过不同的方法实现了基类中的方法。然后需要定义一个工厂类，工厂类可以根据条件生成不同的子类实例。当得到子类的实例后，开发人员可以调用基类中的方法而不必考虑到底返回的是哪一个子类的实例。


94、排序都有哪几种方法？请列举。用JAVA实现一个快速排序。
排序的方法有：插入排序（直接插入排序、希尔排序），交换排序（冒泡排序、快速排序），选择排序（直接选择排序、堆排序），归并排序，分配排序（箱排序、基数排序）
快速排序的伪代码。
/ /使用快速排序方法对a[ 0 :n- 1 ]排序
从a[ 0 :n- 1 ]中选择一个元素作为m i d d l 
e，该元素为支点
把余下的元素分割为两段left 和r i g h t，使得l e f 
t中的元素都小于等于支点，而right 
中的元素都大于等于支点
递归地使用快速排序方法对left 进行排序
递归地使用快速排序方法对right 进行排序
所得结果为l e f t + m i d d l e + r i g h t 


96、JAVA语言如何进行异常处理，关键字：throws,throw,try,catch,finally分别代表什么意义？在try块中可以抛出异常吗？
Java 
通过面向对象的方法进行异常处理，把各种不同的异常进行分类，并提供了良好的接口。在Java中，每个异常都是一个对象，它是Throwable 类或其它子类的实例。当一个方法出现异常后便抛出一个异常对象，该对象中包含有异常信息，调用这个对象的方法可以捕获到这个异常并进行处理。Java的异常处理是通过5 个关键词来实现的：try、catch、throw、throws和finally。一般情况下是用try来执行一段程序，如果出现异常，系统会抛出（throws）一个异常，这时候你可以通过它的类型来捕捉（catch）它，或最后（finally）由缺省处理器来处理。
用try来指定一块预防所有”异常”的程序。紧跟在try程序后面，应包含一个catch子句来指定你想要捕捉的”异常”的类型。
throw语句用来明确地抛出一个”异常”。
throws用来标明一个成员函数可能抛出的各种”异常”。
Finally为确保一段代码不管发生什么”异常”都被执行一段代码。
可以在一个成员函数调用的外面写一个try语句，在这个成员函数内部写另一个try语句保护其他代码。每当遇到一个try语句，”异常”的框架就放到堆栈上面，直到所有的try语句都完成。如果下一级的try语句没有对某种”异常”进行处理，堆栈就会展开，直到遇到有处理这种”异常”的try语句。


97、一个”.java“源文件中是否可以包括多个类（不是内部类）？有什么限制？
可以。必须只有一个类名与文件名相同。


98、MVC的各个部分都有那些技术来实现?如何实现? 
MVC 是Model－View－Controller的简写。”Model” 
代表的是应用的业务逻辑（通过JavaBean，EJB组件实现），
“View” 是应用的表示面（由JSP页面产生），”Controller” 
是提供应用的处理过程控制（一般是一个Servlet），通过这种设计模型把应用逻辑，处理过程和显示逻辑分成不同的组件实现。这些组件可以进行交互和重用。


99、java中有几种方法可以实现一个线程？用什么关键字修饰同步方法? 
stop()和suspend()方法为何不推荐使用？
有两种实现方法，分别是继承Thread类与实现Runnable接口
用synchronized关键字修饰同步方法
反对使用stop()，是因为它不安全。它会解除由线程获取的所有锁定，而且如果对象处于一种不连贯状态，那么其他线程能在那种状态下检查和修改它们。结果很难检查出真正的问题所在。suspend()方法容易发生死锁。调用suspend()的时候，目标线程会停下来，但却仍然持有在这之前获得的锁定。此时，其他任何线程都不能访问锁定的资源，除非被”挂起”的线程恢复运行。对任何线程来说，如果它们想恢复目标线程，同时又试图使用任何一个锁定的资源，就会造成死锁。所以不应该使用suspend()，而应在自己的Thread类中置入一个标志，指出线程应该活动还是挂起。若标志指出线程应该挂起，便用
wait()命其进入等待状态。若标志指出线程应当恢复，则用一个notify()重新启动线程。


100、java中有几种类型的流？JDK为每种类型的流提供了一些抽象类以供继承，请说出他们分别是哪些类？
字节流，字符流。字节流继承于InputStream \ 
OutputStream，字符流继承于InputStreamReader \ 
OutputStreamWriter。在java.io包中还有许多其他的流，主要是为了提高性能和使用方便。
101、java中会存在内存泄漏吗，请简单描述。
会。如：int i,i2; return (i-i2);   //when 
i为足够大的正数,i2为足够大的负数。结果会造成溢位，导致错误。


102、java中实现多态的机制是什么？
方法的重写Overriding和重载Overloading是Java多态性的不同表现。重写Overriding是父类与子类之间多态性的一种表现，重载O verloading是一个类中多态性的一种表现。


103、垃圾回收器的基本原理是什么？垃圾回收器可以马上回收内存吗？有什么办法主动通知虚拟机进行垃圾回收？
对于GC来说，当程序员创建对象时，GC就开始监控这个对象的地址、大小以及使用情况。通常，GC采用有向图的方式记录和管理堆(heap)中的所有对象。通过这种方式确定哪些对象是”可达的”，哪些对象是”不可达的”。当GC确定一些对象为”不可达”时，GC就有责任回收这些内存空间。可以。程序员可以手动执行Sy stem.gc()，通知GC运行，但是Java语言规范并不保证GC一定会执行。


104、静态变量和实例变量的区别？
static i = 10; //常量
class A a; a.i =10;//可变


105、什么是java序列化，如何实现java序列化？
序列化就是一种用来处理对象流的机制，所谓对象流也就是将对象的内容进行流化。可以对流化后的对象进行读写操作，也可将流化后的对象传输于网络之间。序列化是为了解决在对对象流进行读写操作时所引发的问题。
序列化的实现：将需要被序列化的类实现Serializable接口，该接口没有需要实现的方法，implements 
Serializable只是为了标注该对象是可被序列化的，然后使用一个输出流(如：FileOutputStream)来构造一个
ObjectOutputStream(对象流)对象，接着，使用ObjectOutputStream对象的writeObject(Object 
obj)方法就可以将参数为obj的对象写出(即保存其状态)，要恢复的话则用输入流。


106、是否可以从一个static方法内部发出对非static方法的调用？
不可以,如果其中包含对象的method()；不能保证对象初始化. 


107、写clone()方法时，通常都有一行代码，是什么？
Clone 
有缺省行为，super.clone();他负责产生正确大小的空间，并逐位复制。


108、在JAVA中，如何跳出当前的多重嵌套循环？
用break; return 方法。


109、List、Map、Set三个接口，存取元素时，各有什么特点？
List 以特定次序来持有元素，可有重复元素。Set 
无法拥有重复元素,内部排序。Map 
保存key-value值，value可多值。


111、UML方面
标准建模语言UML。用例图,静态图(包括类图、对象图和包图),行为图,交互图(顺序图,合作图),实现图。


 
 
113、开发中都用到了那些设计模式?用在什么场合? 
每个模式都描述了一个在我们的环境中不断出现的问题，然后描述了该问题的解决方案的核心。通过这种方式，你可以无数次地使用那些已有的解决方案，无需在重复相同的工作。主要用到了MVC的设计模式。用来开发JSP/Servlet或者J2EE的相关应用。简单工厂模式等。

115、Anonymous Inner Class (匿名内部类) 
是否可以extends(继承)其它类，是否可以implements(实现)interface(接口)? 
可以继承其他类或完成其他接口，在swing编程中常用此方式。


117、BS与CS的联系与区别。
C/S是Client/Server的缩写。服务器通常采用高性能的PC、工作站或小型机，并采用大型数据库系统，如Oracle、Sybase、Inform ix或
SQL Server。客户端需要安装专用的客户端软件。
B/Ｓ是Brower/Server的缩写，客户机上只要安装一个浏览器（Browser），如Netscape 
Navigator或Internet 
Explorer，服务器安装Oracle、Sybase、Informix或 SQL 
Server等数据库。在这种结构下，用户界面完全通过WWW浏览器实现，一部分事务逻辑在前端实现，但是主要事务逻辑在服务器端实现。浏览器通过Ｗeb 
Server 同数据库进行数据交互。
C/S 与 B/S 区别：
１．硬件环境不同: 
C/S 一般建立在专用的网络上, 
小范围里的网络环境, 
局域网之间再通过专门服务器提供连接和数据交换服务. 
B/S 建立在广域网之上的, 
不必是专门的网络硬件环境,例与电话上网, 租用设备. 
信息自己管理. 有比C/S更强的适应范围, 
一般只要有操作系统和浏览器就行
２．对安全要求不同
C/S 一般面向相对固定的用户群, 
对信息安全的控制能力很强. 
一般高度机密的信息系统采用C/S 结构适宜. 
可以通过B/S发布部分可公开信息. 
B/S 建立在广域网之上, 对安全的控制能力相对弱, 
可能面向不可知的用户。
３．对程序架构不同
C/S 程序可以更加注重流程, 
可以对权限多层次校验, 
对系统运行速度可以较少考虑. 
B/S 对安全以及访问速度的多重的考虑, 
建立在需要更加优化的基础之上. 比C/S有更高的要求
B/S结构的程序架构是发展的趋势, 
从MS的.Net系列的BizTalk 2000 Exchange 2000等, 
全面支持网络的构件搭建的系统. SUN 和IBM推的JavaBean 
构件技术等,使 B/S更加成熟. 
４．软件重用不同
C/S 程序可以不可避免的整体性考虑, 
构件的重用性不如在B/S要求下的构件的重用性好. 
B/S 对的多重结构,要求构件相对独立的功能. 
能够相对较好的重用.就入买来的餐桌可以再利用,而不是做在墙上的石头桌子
５．系统维护不同
C/S 程序由于整体性, 必须整体考察, 
处理出现的问题以及系统升级. 升级难. 
可能是再做一个全新的系统
B/S 
构件组成,方面构件个别的更换,实现系统的无缝升级. 
系统维护开销减到最小.用户从网上自己下载安装就可以实现升级. 
６．处理问题不同
C/S 程序可以处理用户面固定, 并且在相同区域, 
安全要求高需求, 与操作系统相关. 
应该都是相同的系统
B/S 建立在广域网上, 面向不同的用户群, 
分散地域, 这是C/S无法作到的. 
与操作系统平台关系最小. 
７．用户接口不同
C/S 
多是建立的Window平台上,表现方法有限,对程序员普遍要求较高
B/S 建立在浏览器上, 
有更加丰富和生动的表现方式与用户交流. 
并且大部分难度减低,减低开发成本. 
８．信息流不同
C/S 程序一般是典型的中央集权的机械式处理, 
交互性相对低
B/S 信息流向可变化, B-B B-C 
B-G等信息、流向的变化, 更像交易中心。


118、LINUX下线程，GDI类的解释。
LINUX实现的就是基于核心轻量级进程的”一对一”线程模型，一个线程实体对应一个核心轻量级进程，而线程之间的管理在核外函数库中实现。
GDI类为图像设备编程接口类库。
122、WEB 
SERVICE名词解释。JSWDL开发包的介绍。JAXP、JAXM的解释。SOAP、UDDI,WSDL解释。
Web ServiceWeb 
Service是基于网络的、分布式的模块化组件，它执行特定的任务，遵守具体的技术规范，这些规范使得Web 
Service能与其他兼容的组件进行互操作。
JAXP(Java API for XML Parsing) 定义了在Java中使用DOM, SAX, 
XSLT的通用的接口。这样在你的程序中你只要使用这些通用的接口，当你需要改变具体的实现时候也不需要修改代码。
JAXM(Java API for XML Messaging) 
是为SOAP通信提供访问方法和传输机制的API。
WSDL是一种 XML 
格式，用于将网络服务描述为一组端点，这些端点对包含面向文档信息或面向过程信息的消息进行操作。这种格式首先对操作和消息进行抽象描述，然后将其绑定到具体的网络协议和消息格式上以定义端点。相关的具体端点即组合成为抽象端点（服务）。
SOAP即简单对象访问协议(Simple Object Access 
Protocol)，它是用于交换XML编码信息的轻量级协议。
UDDI 
的目的是为电子商务建立标准；UDDI是一套基于Web的、分布式的、为Web 
Service提供的、信息注册中心的实现标准规范，同时也包含一组使企业能将自身提供的Web 
Service注册，以使别的企业能够发现的访问协议的实现标准。
 
123、简述，调试项目出现Exception，你将如何查找？请列出步骤。
 
124、Linux命令
125
115个Java面试题和答案——终极列表（上）
2016-04-30 小马哥 java一日一条

本文我们将要讨论Java面试中的各种不同类型的面试题，它们可以让雇主测试应聘者的Java和通用的面向对象编程的能力。下面的章节分为上下两篇，第一篇将要讨论面向对象编程和它的特点，关于Java和它的功能的常见问题，Java的集合类，垃圾收集器，第二篇主要讨论异常处理，Java小应用程序，Swing，JDBC，远程方法调用(RMI)，Servlet和JSP。
开始！
目录
面向对象编程（OOP）
常见的Java问题
Java线程
Java集合类
垃圾收集器
面向对象编程（OOP）
Java是一个支持并发、基于类和面向对象的计算机编程语言。下面列出了面向对象软件开发的优点：
代码开发模块化，更易维护和修改。
代码复用。
增强代码的可靠性和灵活性。
增加代码的可理解性。
面向对象编程有很多重要的特性，比如：封装，继承，多态和抽象。下面的章节我们会逐个分析这些特性。
封装
封装给对象提供了隐藏内部特性和行为的能力。对象提供一些能被其他对象访问的方法来改变它内部的数据。在Java当中，有3种修饰符：public，private和protected。每一种修饰符给其他的位于同一个包或者不同包下面对象赋予了不同的访问权限。
下面列出了使用封装的一些好处：
通过隐藏对象的属性来保护对象内部的状态。
提高了代码的可用性和可维护性，因为对象的行为可以被单独的改变或者是扩展。
禁止对象之间的不良交互提高模块化。
参考这个文档获取更多关于封装的细节和示例。
多态
多态是编程语言给不同的底层数据类型做相同的接口展示的一种能力。一个多态类型上的操作可以应用到其他类型的值上面。
继承
继承给对象提供了从基类获取字段和方法的能力。继承提供了代码的重用行，也可以在不修改类的情况下给现存的类添加新特性。
抽象
抽象是把想法从具体的实例中分离出来的步骤，因此，要根据他们的功能而不是实现细节来创建类。Java支持创建只暴漏接口而不包含方法实现的抽象的类。这种抽象技术的主要目的是把类的行为和实现细节分离开。
抽象和封装的不同点
抽象和封装是互补的概念。一方面，抽象关注对象的行为。另一方面，封装关注对象行为的细节。一般是通过隐藏对象内部状态信息做到封装，因此，封装可以看成是用来提供抽象的一种策略。
常见的Java问题
1.什么是Java虚拟机？为什么Java被称作是“平台无关的编程语言”？
Java虚拟机是一个可以执行Java字节码的虚拟机进程。Java源文件被编译成能被Java虚拟机执行的字节码文件。
Java被设计成允许应用程序可以运行在任意的平台，而不需要程序员为每一个平台单独重写或者是重新编译。Java虚拟机让这个变为可能，因为它知道底层硬件平台的指令长度和其他特性。
2.JDK和JRE的区别是什么？
Java运行时环境(JRE)是将要执行Java程序的Java虚拟机。它同时也包含了执行applet需要的浏览器插件。Java开发工具包(JDK)是完整的Java软件开发包，包含了JRE，编译器和其他的工具(比如：JavaDoc，Java调试器)，可以让开发者开发、编译、执行Java应用程序。
3.”static”关键字是什么意思？Java中是否可以覆盖(override)一个private或者是static的方法？
“static”关键字表明一个成员变量或者是成员方法可以在没有所属的类的实例变量的情况下被访问。
Java中static方法不能被覆盖，因为方法覆盖是基于运行时动态绑定的，而static方法是编译时静态绑定的。static方法跟类的任何实例都不相关，所以概念上不适用。
4.是否可以在static环境中访问非static变量？
static变量在Java中是属于类的，它在所有的实例中的值是一样的。当类被Java虚拟机载入的时候，会对static变量进行初始化。如果你的代码尝试不用实例来访问非static的变量，编译器会报错，因为这些变量还没有被创建出来，还没有跟任何实例关联上。
5.Java支持的数据类型有哪些？什么是自动拆装箱？
Java语言支持的8中基本数据类型是：
byte
short
int
long
float
double
boolean
char
自动装箱是Java编译器在基本数据类型和对应的对象包装类型之间做的一个转化。比如：把int转化成Integer，double转化成double，等等。反之就是自动拆箱。
6.Java中的方法覆盖(Overriding)和方法重载(Overloading)是什么意思？
Java中的方法重载发生在同一个类里面两个或者是多个方法的方法名相同但是参数不同的情况。与此相对，方法覆盖是说子类重新定义了父类的方法。方法覆盖必须有相同的方法名，参数列表和返回类型。覆盖者可能不会限制它所覆盖的方法的访问。
7.Java中，什么是构造函数？什么是构造函数重载？什么是复制构造函数？
当新对象被创建的时候，构造函数会被调用。每一个类都有构造函数。在程序员没有给类提供构造函数的情况下，Java编译器会为这个类创建一个默认的构造函数。
Java中构造函数重载和方法重载很相似。可以为一个类创建多个构造函数。每一个构造函数必须有它自己唯一的参数列表。
Java不支持像C++中那样的复制构造函数，这个不同点是因为如果你不自己写构造函数的情况下，Java不会创建默认的复制构造函数。
8.Java支持多继承么？
不支持，Java不支持多继承。每个类都只能继承一个类，但是可以实现多个接口。
9.接口和抽象类的区别是什么？
Java提供和支持创建抽象类和接口。它们的实现有共同点，不同点在于：
接口中所有的方法隐含的都是抽象的。而抽象类则可以同时包含抽象和非抽象的方法。
类可以实现很多个接口，但是只能继承一个抽象类
类如果要实现一个接口，它必须要实现接口声明的所有方法。但是，类可以不实现抽象类声明的所有方法，当然，在这种情况下，类也必须得声明成是抽象的。
抽象类可以在不提供接口方法实现的情况下实现接口。
Java接口中声明的变量默认都是final的。抽象类可以包含非final的变量。
Java接口中的成员函数默认是public的。抽象类的成员函数可以是private，protected或者是public。
接口是绝对抽象的，不可以被实例化。抽象类也不可以被实例化，但是，如果它包含main方法的话是可以被调用的。
也可以参考JDK8中抽象类和接口的区别
10.什么是值传递和引用传递？
对象被值传递，意味着传递了对象的一个副本。因此，就算是改变了对象副本，也不会影响源对象的值。
对象被引用传递，意味着传递的并不是实际的对象，而是对象的引用。因此，外部对引用对象所做的改变会反映到所有的对象上。
Java线程
11.进程和线程的区别是什么？
进程是执行着的应用程序，而线程是进程内部的一个执行序列。一个进程可以有多个线程。线程又叫做轻量级进程。
12.创建线程有几种不同的方式？你喜欢哪一种？为什么？
有三种方式可以用来创建线程：
继承Thread类
实现Runnable接口
应用程序可以使用Executor框架来创建线程池
实现Runnable接口这种方式更受欢迎，因为这不需要继承Thread类。在应用设计中已经继承了别的对象的情况下，这需要多继承（而Java不支持多继承），只能实现接口。同时，线程池也是非常高效的，很容易实现和使用。
13.概括的解释下线程的几种可用状态。
线程在执行过程中，可以处于下面几种状态：
就绪(Runnable):线程准备运行，不一定立马就能开始执行。
运行中(Running)：进程正在执行线程的代码。
等待中(Waiting):线程处于阻塞的状态，等待外部的处理结束。
睡眠中(Sleeping)：线程被强制睡眠。
I/O阻塞(Blocked on I/O)：等待I/O操作完成。
同步阻塞(Blocked on Synchronization)：等待获取锁。
死亡(Dead)：线程完成了执行。
14.同步方法和同步代码块的区别是什么？
在Java语言中，每一个对象有一把锁。线程可以使用synchronized关键字来获取对象上的锁。synchronized关键字可应用在方法级别(粗粒度锁)或者是代码块级别(细粒度锁)。
15.在监视器(Monitor)内部，是如何做线程同步的？程序应该做哪种级别的同步？
监视器和锁在Java虚拟机中是一块使用的。监视器监视一块同步代码块，确保一次只有一个线程执行同步代码块。每一个监视器都和一个对象引用相关联。线程在获取锁之前不允许执行同步代码。
16.什么是死锁(deadlock)？
两个进程都在等待对方执行完毕才能继续往下执行的时候就发生了死锁。结果就是两个进程都陷入了无限的等待中。
17.如何确保N个线程可以访问N个资源同时又不导致死锁？
使用多线程的时候，一种非常简单的避免死锁的方式就是：指定获取锁的顺序，并强制线程按照指定的顺序获取锁。因此，如果所有的线程都是以同样的顺序加锁和释放锁，就不会出现死锁了。
Java集合类
18.Java集合类框架的基本接口有哪些？
Java集合类提供了一套设计良好的支持对一组对象进行操作的接口和类。Java集合类里面最基本的接口有：
Collection：代表一组对象，每一个对象都是它的子元素。
Set：不包含重复元素的Collection。
List：有顺序的collection，并且可以包含重复元素。
Map：可以把键(key)映射到值(value)的对象，键不能重复。
19.为什么集合类没有实现Cloneable和Serializable接口？
集合类接口指定了一组叫做元素的对象。集合类接口的每一种具体的实现类都可以选择以它自己的方式对元素进行保存和排序。有的集合类允许重复的键，有些不允许。
20.什么是迭代器(Iterator)？
Iterator接口提供了很多对集合元素进行迭代的方法。每一个集合类都包含了可以返回迭代器实例的
迭代方法。迭代器可以在迭代的过程中删除底层集合的元素。
克隆(cloning)或者是序列化(serialization)的语义和含义是跟具体的实现相关的。因此，应该由集合类的具体实现来决定如何被克隆或者是序列化。
21.Iterator和ListIterator的区别是什么？
下面列出了他们的区别：
Iterator可用来遍历Set和List集合，但是ListIterator只能用来遍历List。
Iterator对集合只能是前向遍历，ListIterator既可以前向也可以后向。
ListIterator实现了Iterator接口，并包含其他的功能，比如：增加元素，替换元素，获取前一个和后一个元素的索引，等等。
22.快速失败(fail-fast)和安全失败(fail-safe)的区别是什么？
Iterator的安全失败是基于对底层集合做拷贝，因此，它不受源集合上修改的影响。java.util包下面的所有的集合类都是快速失败的，而java.util.concurrent包下面的所有的类都是安全失败的。快速失败的迭代器会抛出ConcurrentModificationException异常，而安全失败的迭代器永远不会抛出这样的异常。
23.Java中的HashMap的工作原理是什么？
Java中的HashMap是以键值对(key-value)的形式存储元素的。HashMap需要一个hash函数，它使用hashCode()和equals()方法来向集合/从集合添加和检索元素。当调用put()方法的时候，HashMap会计算key的hash值，然后把键值对存储在集合中合适的索引上。如果key已经存在了，value会被更新成新值。HashMap的一些重要的特性是它的容量(capacity)，负载因子(load factor)和扩容极限(threshold resizing)。
24.hashCode()和equals()方法的重要性体现在什么地方？
Java中的HashMap使用hashCode()和equals()方法来确定键值对的索引，当根据键获取值的时候也会用到这两个方法。如果没有正确的实现这两个方法，两个不同的键可能会有相同的hash值，因此，可能会被集合认为是相等的。而且，这两个方法也用来发现重复元素。所以这两个方法的实现对HashMap的精确性和正确性是至关重要的。
25.HashMap和Hashtable有什么区别？
HashMap和Hashtable都实现了Map接口，因此很多特性非常相似。但是，他们有以下不同点：
HashMap允许键和值是null，而Hashtable不允许键或者值是null。
Hashtable是同步的，而HashMap不是。因此，HashMap更适合于单线程环境，而Hashtable适合于多线程环境。
HashMap提供了可供应用迭代的键的集合，因此，HashMap是快速失败的。另一方面，Hashtable提供了对键的列举(Enumeration)。
o一般认为Hashtable是一个遗留的类。
26.数组(Array)和列表(ArrayList)有什么区别？什么时候应该使用Array而不是ArrayList？
下面列出了Array和ArrayList的不同点：
Array可以包含基本类型和对象类型，ArrayList只能包含对象类型。
Array大小是固定的，ArrayList的大小是动态变化的。
ArrayList提供了更多的方法和特性，比如：addAll()，removeAll()，iterator()等等。
对于基本类型数据，集合使用自动装箱来减少编码工作量。但是，当处理固定大小的基本数据类型的时候，这种方式相对比较慢。
27.ArrayList和LinkedList有什么区别？
ArrayList和LinkedList都实现了List接口，他们有以下的不同点：
ArrayList是基于索引的数据接口，它的底层是数组。它可以以O(1)时间复杂度对元素进行随机访问。与此对应，LinkedList是以元素列表的形式存储它的数据，每一个元素都和它的前一个和后一个元素链接在一起，在这种情况下，查找某个元素的时间复杂度是O(n)。
相对于ArrayList，LinkedList的插入，添加，删除操作速度更快，因为当元素被添加到集合任意位置的时候，不需要像数组那样重新计算大小或者是更新索引。
LinkedList比ArrayList更占内存，因为LinkedList为每一个节点存储了两个引用，一个指向前一个元素，一个指向下一个元素。
也可以参考ArrayList vs. LinkedList。
28.Comparable和Comparator接口是干什么的？列出它们的区别。
Java提供了只包含一个compareTo()方法的Comparable接口。这个方法可以个给两个对象排序。具体来说，它返回负数，0，正数来表明输入对象小于，等于，大于已经存在的对象。
Java提供了包含compare()和equals()两个方法的Comparator接口。compare()方法用来给两个输入参数排序，返回负数，0，正数表明第一个参数是小于，等于，大于第二个参数。equals()方法需要一个对象作为参数，它用来决定输入参数是否和comparator相等。只有当输入参数也是一个comparator并且输入参数和当前comparator的排序结果是相同的时候，这个方法才返回true。
29.什么是Java优先级队列(Priority Queue)？
PriorityQueue是一个基于优先级堆的无界队列，它的元素是按照自然顺序(natural order)排序的。在创建的时候，我们可以给它提供一个负责给元素排序的比较器。PriorityQueue不允许null值，因为他们没有自然顺序，或者说他们没有任何的相关联的比较器。最后，PriorityQueue不是线程安全的，入队和出队的时间复杂度是O(log(n))。
30.你了解大O符号(big-O notation)么？你能给出不同数据结构的例子么？
大O符号描述了当数据结构里面的元素增加的时候，算法的规模或者是性能在最坏的场景下有多么好。
大O符号也可用来描述其他的行为，比如：内存消耗。因为集合类实际上是数据结构，我们一般使用大O符号基于时间，内存和性能来选择最好的实现。大O符号可以对大量数据的性能给出一个很好的说明。
31.如何权衡是使用无序的数组还是有序的数组？
有序数组最大的好处在于查找的时间复杂度是O(log n)，而无序数组是O(n)。有序数组的缺点是插入操作的时间复杂度是O(n)，因为值大的元素需要往后移动来给新元素腾位置。相反，无序数组的插入时间复杂度是常量O(1)。
32.Java集合类框架的最佳实践有哪些？
根据应用的需要正确选择要使用的集合的类型对性能非常重要，比如：假如元素的大小是固定的，而且能事先知道，我们就应该用Array而不是ArrayList。
有些集合类允许指定初始容量。因此，如果我们能估计出存储的元素的数目，我们可以设置初始容量来避免重新计算hash值或者是扩容。
为了类型安全，可读性和健壮性的原因总是要使用泛型。同时，使用泛型还可以避免运行时的ClassCastException。
使用JDK提供的不变类(immutable class)作为Map的键可以避免为我们自己的类实现hashCode()和equals()方法。
编程的时候接口优于实现。
底层的集合实际上是空的情况下，返回长度是0的集合或者是数组，不要返回null。
33.Enumeration接口和Iterator接口的区别有哪些？
Enumeration速度是Iterator的2倍，同时占用更少的内存。但是，Iterator远远比Enumeration安全，因为其他线程不能够修改正在被iterator遍历的集合里面的对象。同时，Iterator允许调用者删除底层集合里面的元素，这对Enumeration来说是不可能的。
34.HashSet和TreeSet有什么区别？
HashSet是由一个hash表来实现的，因此，它的元素是无序的。add()，remove()，contains()方法的时间复杂度是O(1)。
另一方面，TreeSet是由一个树形的结构来实现的，它里面的元素是有序的。因此，add()，remove()，contains()方法的时间复杂度是O(logn)。
垃圾收集器(Garbage Collectors)
35.Java中垃圾回收有什么目的？什么时候进行垃圾回收？
垃圾回收的目的是识别并且丢弃应用不再使用的对象来释放和重用资源。
36.System.gc()和Runtime.gc()会做什么事情？
这两个方法用来提示JVM要进行垃圾回收。但是，立即开始还是延迟进行垃圾回收是取决于JVM的。
37.finalize()方法什么时候被调用？析构函数(finalization)的目的是什么？
在释放对象占用的内存之前，垃圾收集器会调用对象的finalize()方法。一般建议在该方法中释放对象持有的资源。
38.如果对象的引用被置为null，垃圾收集器是否会立即释放对象占用的内存？
不会，在下一个垃圾回收周期中，这个对象将是可被回收的。
39.Java堆的结构是什么样子的？什么是堆中的永久代(Perm Gen space)?
JVM的堆是运行时数据区，所有类的实例和数组都是在堆上分配内存。它在JVM启动的时候被创建。对象所占的堆内存是由自动内存管理系统也就是垃圾收集器回收。
堆内存是由存活和死亡的对象组成的。存活的对象是应用可以访问的，不会被垃圾回收。死亡的对象是应用不可访问尚且还没有被垃圾收集器回收掉的对象。一直到垃圾收集器把这些对象回收掉之前，他们会一直占据堆内存空间。
40.串行(serial)收集器和吞吐量(throughput)收集器的区别是什么？
吞吐量收集器使用并行版本的新生代垃圾收集器，它用于中等规模和大规模数据的应用程序。而串行收集器对大多数的小应用(在现代处理器上需要大概100M左右的内存)就足够了。
41.在Java中，对象什么时候可以被垃圾回收？
当对象对当前使用这个对象的应用程序变得不可触及的时候，这个对象就可以被回收了。
42.JVM的永久代中会发生垃圾回收么？
垃圾回收不会发生在永久代，如果永久代满了或者是超过了临界值，会触发完全垃圾回收(Full GC)。如果你仔细查看垃圾收集器的输出信息，就会发现永久代也是被回收的。这就是为什么正确的永久代大小对避免Full GC是非常重要的原因。请参考下Java8：从永久代到元数据区
(译者注：Java8中已经移除了永久代，新加了一个叫做元数据区的native内存区)

阅读原文
阅读 2195
13投诉
