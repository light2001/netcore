### .Net 面试题整理
#### 模块划分
- .netcore框架部分
- c#基础部分
- Linux部分
- clr部分
- 中间件部分
- 数据库部分
- 架构设计部分
- 算法部分


#### .netcore框架面试题

第二题，asp dot core有哪些好的功能？
1. 是依赖注入。
2. 是日志系统架构。
3. 是引入了一个跨平台的网络服务器，kestrel。可以没有iis, apache和nginx就可以单独运行。
4. 是可以使用命令行创建应用。
5. 是使用APP settings json file来配置工程。
6. 是使用start up来注册服务。
7. 是更好的支持异步编程。
8. 是支持web socket和signal IR。
9. 是对于跨网站的请求的预防和保护机制。



第三题，dot net core跟dot net比较有哪些更好的地方？
1.是跨平台，它可以运行在三大操作系统上面，windows， Linux和MAC。
2.是对架构本身安装没有依赖，因为所有的依赖都跟程序本身在一起。
3.是dot net core处理请求的效率更高，能够处理更多的请求。
4.是dot net core有更多的安装配置方法。


 
第四题什么是meta packages？
Meta packages是指包含所有ASP dot net code依赖的一个包。叫做Microsoft.AspNetCore



第五题，don net core应用能够跟dot net 4.x架构一起工作吗？
可以。Dot net core应用可以跟标准的dot net 库一起工作。

第六题，什么是dot net core的startup class？
Startup class是dot net core应用的入口。所有的dot net core应用必须有这个class。这个类用来配置应用。这个类的调用是在program main函数里面进行配置的。类的名字可以自己定义。
 
第七题, Startup class的config service方法有什么作用?
在这个方法里我们可以添加一些service进入依赖注入容器。
 
第八题，startup class的configure方法有什么作用？
这个方法来定义整个应用如何响应HTTP请求。它有几个比较重要的参数，application builder，Hosting environment, logo factory， 在这里我们可以配置一些中间件用来处理路径，验证和session等等。
 
第九题，什么是中间件？
中间件在这里是指注入到应用中处理请求和响应的组件。
 
第十题，application builder的use和run方法有什么区别？
这两个方法都在start up class的configure方法里面调用。都是用来向应用请求管道里面添加中间件的。Use方法可以调用下一个中间件的添加，而run不会。
 
第十一题，dot net core 管道里面的map拓展有什么作用?
可以针对不同的路径添加不同的中间件。
 
第十二题，dot net core里面的路径是如何处理的？
路径处理是用来为进入的请求寻找处理函数的机制。所有的路径在函数运行开始时进行注册。
主要有两种路径处理方式， 常规路径处理和属性路径处理。常规路径处理就是用MapRoute的方式设定调用路径，属性路径处理是指在调用函数的上方设定一个路径属性。
 
第十三题，如何在dot net core中激活session功能?
首先要添加session包. 其次要在config service方法里面添加session。然后又在configure方法里面调用usesession。
 
第十四题，dot net core工程里面有多少个工程文件?
global, launch setting，app settings，bundle config，bower, package。
 
第十五题，什么是dot net core里面的tag helper?
Tag helper用来在服务器端使用Razor视图引擎创建html元素的。
 
第十六题， 如何使tag helper在元素这一层上失效?
使用叹号。
 
第十七题，什么是Razor页面?
是dot net core中支持ASP网页表格的一种开发模型。@page 作为页面的起始标志。
  
第十八题，如何在Razor页面中实现数据模型绑定?
使用bindproperty属性。
 
第十九题, 如何在controller中注入service?
在config services方法中配置这个service。
在controller的构造函数中，添加这个依赖注入。
 
第二十题，描述一下依赖注入后的服务生命周期?
在dot net core中，我们不需要关心如何释放这些服务, 因为系统会帮我们释放掉。有三种服务的生命周期。
单实例服务， 通过add singleton方法来添加。在注册时即创建服务, 在随后的请求中都使用这一个服务。
短暂服务, 通过add transient方法来添加。是一种轻量级的服务，用于无状态服务的操作。
作用域服务，一个新的请求会创建一个服务实例。使用add scoped方法来添加。

Startup里面有哪些方法，分别是用来做什么的
EF的封装，多数据源，扩展表达式，怎么生成数据库,  如果要提升效率有哪些注意点
.net core 部署在linux下如何做，同时监听多个端口怎么做
linux问题
怎么处理时区，怎么查找程序装在哪里，centos不维护了怎么办
cicd怎么处理
.net core 怎么解决跨域问题
.netcore2.2的路由和3.1有什么区别
怎么接入Autofac，把ioc容器换了

#### C# 基础面试题

● 继承，接口，抽象类，引用，ref out,代理，反射，事件
● C#有几种委托，区别是什么
● C#有哪些集合类，这些类的区别是什么
● 泛型，有哪些约束条件
● 元组
● 表达式树怎么封装
● 扩展方法是什么，怎么用
● 什么是PLinq，他是如何工作的
● Task是什么，怎么使用，和ThreadPool的区别是什么
● TaskSchedule是什么，怎么工作
● Async和Await是做什么的
● 怎么用c#实现订阅发布模式
● 怎么用c#实现事件委托模型


C#有几种委托，区别是什么
https://www.cnblogs.com/xiao-qian/p/12688043.html
2.1 delegate
        public delegate int TestDelegate(int x, int y);
2.2 Action
       Action是无返回值的泛型委托。
Action 表示无参，无返回值的委托
Action<int,string> 表示有传入参数int,string无返回值的委托
2.3 Func
Func是有返回值的泛型委托
Func<int> 表示无参，返回值为int的委托
Func<object,string,int> 表示传入参数为object, string 返回值为int的委托
2.4 predicate
predicate 是返回bool型的泛型委托
predicate<int> 表示传入参数为int 返回bool的委托。
2.5 四者之间的区别
Delegate至少0个参数，至多32个参数，可以无返回值，也可以指定返回值类型
Action至少1个参数，至多4个参数，无返回值，
Func至少0个参数，至多4个参数，根据返回值泛型返回。必须有返回值，不可void
Predicate至少1个参数，至多1个参数，返回值固定为bool


1、值类型与引用类型
值类型：struct、enum、int、float、char、bool、decimal
引用类型：class、delegate、interface、array、object、string
2、装箱与拆箱
装箱：把值类型转换成引用类型
拆箱：把引用类型转换成值类型
装箱：对值类型在堆中分配一个对象实例，并将该值复制到新的对象中。
（1）第一步：新分配托管堆内存(大小为值类型实例大小加上一个方法表指针。
（2）第二步：将值类型的实例字段拷贝到新分配的内存中。
（3）第三步：返回托管堆中新分配对象的地址。这个地址就是一个指向对象的引用了。
拆箱：检查对象实例，确保它是给定值类型的一个装箱值。将该值从实例复制到值类型变量中。
在装箱时是不需要显式的类型转换的，不过拆箱需要显式的类型转换。
3、堆和栈
存放在栈中时要管存储顺序，保持着先进后出的原则，他是一片连续的内存域，有系统自动分配和维护；
堆是无序的，他是一片不连续的内存域，有用户自己来控制和释放，如果用户自己不释放的话，当内存达到一定的特定值时，通过垃圾回收器(GC)来回收。
栈内存无需我们管理，也不受GC管理。当栈顶元素使用完毕，立马释放。而堆则需要GC清理。
使用引用类型的时候，一般是对指针进行的操作而非引用类型对象本身。但是值类型则操作其本身。
4、GC（Garbage Collection）
当程序需要更多的堆空间时，GC需要进行垃圾清理工作，暂停所有线程，找出所有无被引用的对象，进行清理，并通知栈中的指针重新指向地址排序后的对象。
GC只能处理托管内存资源的释放，对于非托管资源则不能使用GC进行回收，必须由程序员手动回收，例如FileStream或SqlConnection需要调用Dispose进行资源的回收。
5、CLR（Common Language Runtime）
公共语言运行库，负责资源管理（包括内存分配、程序及加载、异常处理、线程同步、垃圾回收等），并保证应用和底层操作系统的分离。
6、静态构造函数
最先被执行的构造函数，且在一个类里只允许有一个无参的静态构造函数
执行顺序：静态变量>静态构造函数>实例变量>实例构造函数
7、文件I/O
通过流的方式对文件进行读写操作
（1）FileStream
（2）StreamReader/StreamWriter
8、序列化与反序列化
序列化：将对象状态转换为可保持或传输的格式的过程。将对象实例的字段及类的名称转换成字节流，然后把字节流写入数据流
反序列化：将流转换为对象。
这两个过程结合起来，可以轻松地存储和传输数据。
9、线程同步
（1）方法一：阻塞（调用Sleep()或Join()）
（2）方法二：加互斥锁lock
（3）方法三：信号和句柄（AutoResetEvent/ManualResetEvent，调用Set()和WaitOne()）
10、抽象类abstract class与接口interface的异同
相同点：
（1）都可以被继承
（2）都不能被实例化
（3）都可以包含方法的声明
不同点：
（1）抽象类被子类继承；接口被类实现
（2）抽象类只能被单个类继承；接口可继承接口，并可多继承接口
（3）抽象基类可以定义字段、属性、方法实现；接口只能定义属性、索引器、事件、和方法声明，不能包含字段
（4）抽象类可以做方法声明，也可做方法实现；接口只能做方法声明
（5）具体派生类必须覆盖(override)抽象基类的抽象方法；派生类必须实现接口的所有方法
（6）抽象类是一个不完整的类，需要进一步细化；接口是一个行为规范
（7）抽象类中的虚方法或抽象方法必须用public修饰；接口中的所有成员默认为public，不能有private修饰符
11、类class与结构体struct的异同
Class属于引用类型，是分配在内存的堆上的；
Struct属于值类型，是分配在内存的栈上的；不能从另外一个结构或者类继承，本身也不能被继承；没有默认的构造函数，但是可以添加构造函数；可以不使用new 初始化
12、using关键字的使用场景
（1）作为指令：用于导入其他命名空间中定义的类型或为命名空间创建别名
（2）作为语句：用于定义一个范围，在此范围的末尾将释放对象
13、new关键字的使用场景
（1）实例化对象
（2）隐藏父类方法
14、委托与事件
委托可以把一个方法作为参数传入另一个方法，可以理解为指向一个函数的引用；
事件是一种特殊的委托。
15、重载(overload)与重写(override)的区别
重载：是方法的名称相同，参数或参数类型不同；重载是面向过程的概念。
重写：是对基类中的虚方法进行重写。重写是面向对象的概念。
16、return执行顺序
try{} 里有一个return语句，那么finally{} 里的code在return前执行。
17、switch(expression)
其中expression支持任何数据类型，包括null。
18、反射Reflection
动态获取程序集信息。
19、property与attribute的区别
property是属性，用于存取类的字段；
attribute是特性，用来标识类，方法等的附加性质。
20、访问修饰符
（1）public 公有访问，不受任何限制。
（2）private 私有访问，只限于本类成员访问。
（3）protected 保护访问，只限于本类和子类访问。
（4）internal 内部访问，只限于当前程序集内访问。
21、static关键字的应用
对类有意义的字段和方法使用static关键字修饰，称为静态成员，通过类名加访问操作符“.”进行访问; 对类的实例有意义的字段和方法不加static关键字，称为非静态成员或实例成员。
注: 静态字段在内存中只有一个拷贝，非静态字段则是在每个实例对象中拥有一个拷贝。而方法无论是否为静态，在内存中只会有一份拷贝，区别只是通过类名来访问还是通过实例名来访问。
23、值传递与引用传递
值传递时，系统首先为被调用方法的形参分配内存空间，并将实参的值按位置一一对应地复制给形参，此后，被调用方法中形参值得任何改变都不会影响到相应的实参；
引用传递时，系统不是将实参本身的值复制后传递给形参，而是将其引用值（即地址值）传递给形参，因此，形参所引用的该地址上的变量与传递的实参相同，方法体内相应形参值得任何改变都将影响到作为引用传递的实参。
简而言之，按值传递不是值参数是值类型，而是指形参变量会复制实参变量，也就是会在栈上多创建一个相同的变量。而按引用传递则不会。可以通过 ref 和 out 来决定参数是否按照引用传递。
24、参数传递 ref 与 out 的区别
（1）ref指定的参数在函数调用时必须先初始化，而out不用
（2）out指定的参数在进入函数时会清空自己，因此必须在函数内部进行初始化赋值操作，而ref不用
总结：ref可以把值传到方法里，也可以把值传到方法外；out只可以把值传到方法外
注意：string作为特殊的引用类型，其操作是与值类型看齐的，若要将方法内对形参赋值后的结果传递出来，需要加上ref或out关键字。
25、浅克隆与深克隆（浅拷贝与深拷贝）
（1）浅克隆
在浅克隆中，如果原型对象的成员变量是值类型，将复制一份给克隆对象；如果原型对象的成员变量是引用类型，则将引用对象的地址复制一份给克隆对象，也就是说原型对象和克隆对象的成员变量指向相同的内存地址。简单来说，在浅克隆中，当对象被复制时只复制它本身和其中包含的值类型的成员变量，而引用类型的成员对象并没有复制，如图：

通过实现ICloneable接口的Clone()方法，并调用MemberwiseClone()方法来实现浅克隆
（2）深克隆
在深克隆中，无论原型对象的成员变量是值类型还是引用类型，都将复制一份给克隆对象，深克隆将原型对象的所有引用对象也复制一份给克隆对象。简单来说，在深克隆中，除了对象本身被复制外，对象所包含的所有成员变量也将复制，如图：
在C#语言中，如果需要实现深克隆，可以通过序列化(Serialization)等方式来实现。序列化就是将对象写到流的过程，写到流中的对象是原有对象的一个拷贝，而原对象仍然存在于内存中。通过序列化实现的拷贝不仅可以复制对象本身，而且可以复制其引用的成员对象，因此通过序列化将对象写到一个流中，再从流里将其读出来，可以实现深克隆。需要注意的是能够实现序列化的对象其类必须实现Serializable接口，否则无法实现序列化操作。




#### Linux部分


基础题目
● 常用的linux命令，列举5个
● 如何查出程序装在哪里
● linux的目录结构
● 怎么查找日志最后5行，前5行
● 时区怎么设置

扩展问题
● 网卡怎么设置，ip地址，dhcp ,开机自启动
● 怎么自定义开机启动项
● 环境变量怎么设置
● 怎么设置软件镜像
● 挂载分区，动态磁盘扩容





#### CLR面试题



#### 中间件面试题
redis，nginx，rabbitmq，kafka，链路跟踪


#### 数据库面试题
1、数据库操作的相关类
特定类：Connection，Command，CommandBuilder，DataAdapter，DataReader，Parameter，Transaction
共享类：DataSet，DataTable，DataRow，DataColumn，DataRealtion，Constraint，DataColumnMapping，DataTableMapping
（1）Connection：开启程序与数据库之间的连接。
（2）Command：对数据库发送一些指令。例如增删改查等指令，以及调用存在数据库中的存储过程等。
（3）DataAdapter：主要在数据源及DataSet 之间执行传输工作，通过Command 下达命令后，将取得的数据放进DataSet对象中。
（4）DataSet：这个对象可视为一个暂存区(Cache),可以把数据库中所查询到的数据保存起来，甚至可以将整个数据库显示出来，DataSet是放在内存中的。
备注：将DataAdapter对象当做DataSet 对象与数据源间传输数据的桥梁。DataSet包含若干DataTable、DataTableTable包含若干DataRow。
（5）DataReader：一笔向下循序的读取数据源中的数据。
总结：http://ADO.NET 使用Connection对象来连接数据库，使用Command或DataAdapter对象来执行SQL语句，并将执行的结果返回给DataReader或DataAdapter，然后再使用取得的DataReader或DataAdapter对象操作数据结果。
2、事务
3、索引
4、视图
5、存储过程
6、慢查询如何定位，优化


#### 架构设计部分
● .net程序占用资源过高，怎么定位问题
● 高并发怎么处理，秒杀，团购，抢购等
● 分布式cap定理
● ddd（领域驱动）是什么，怎么落地
● 怎么用.net实现微服务


#### 算法部分
1. 红包随机分配，怎么做
N块钱，分给M个人

2. 运费，多仓库，最短路径


3. 给出一个 32 位的有符号整数，你需要将这个整数中每位上的数字进行反转。


4. 一个长度为n-1的递增排序数组中的所有数字都是唯一的，并且每个数字都在范围0～n-1之内。在范围0～n-1内的n个数字中有且只有一个数字不在该数组中，请找出这个数字。



外链：
c# 
https://blog.csdn.net/zlbdmm/article/details/103788924
https://www.cnblogs.com/cyq1162/p/9073634.html
https://www.bbsmax.com/A/Vx5MD0PaJN/
https://www.jianshu.com/p/829716682d5d
基础问题
https://www.runoob.com/csharp/csharp-multithreading.html




Linux:
https://blog.csdn.net/a303549861/article/details/93754526
https://www.cnblogs.com/yitao326/p/10135526.html



