第一节：编码过程的命名约定（编码命名规范）
 

======================================================================================

====================================PHP编码规范=======================================
======================================================================================


PSR（PHP Standard Recommendations，PHP标准规范） 是由PHP FIG组织制定的PHP规范，是PHP开发的实践标准。主要包含基础编码规范、编码风格规范、日志接口规范、缓存接口规范、HTTP消息接口规范等。

1. 【必须】代码必须使用4个空格符而不是「Tab 键」进行缩进。使用空格而不是「tab键缩进」的好处在于， 避免在比较代码差异、打补丁、重阅代码以及注释时产生混淆。 并且，使用空格缩进，让对齐变得更方便。
2. 【必须】类的属性和方法必须添加访问修饰符（private、protected 以及 public），abstract 以及 final 必须声明在访问修饰符之前，而 static 必须声明在访问修饰符之后。
3. 【必须】PHP所有关键字必须全部小写。常量 true 、false 和 null 也 必须 全部小写。
4. 【不该】类的属性和方法不该使用下划线作为前缀，来区分是 protected 或 private。

目录和文件
目录使用小写+下划线。（参考linux目录命名，全部小写，linux目录单词间没有分隔符，如/var/spool/clientqueue,/etc/inittab,/bin/dnsdomainname等）
类的文件名均以命名空间定义，并且命名空间的路径和类库文件所在路径一致。
类文件采用大驼峰法命名（首字母大写），其它文件采用小写+下划线命名。
类名和类文件名保持一致，统一采用大驼峰法命名（首字母大写）。

函数和类、属性命名
类的命名采用大驼峰法（首字母大写），例如 User、UserType，默认不需要添加后缀，例如UserController应该直接命名为User。
函数的命名使用小写字母和下划线（小写字母开头）的方式，例如 get_client_ip。
方法的命名使用小驼峰法（首字母小写），一般使用动词+名词的形式来描述该方法的功能，如sendMessage()发送短信，getUserName()获取用户名。
属性的命名使用小驼峰法（首字母小写），例如 tableName、instance。(属性的类型可以在phpdoc中标识，因此属性名称无需考虑类型前缀来标识，如 /** @var integer */ protected $sex=0;)
变量的命名使用小驼峰法（首字母小写），建议在变量前加表示类型的前缀。例如 $intSex=0;$intLoginErrorCount=0。 (变量名称无法使用phpdoc，因此建议增加类型前缀标识)
以双下划线“__”打头的函数或方法作为魔术方法，例如 __call 和 __autoload。

常量和配置
常量以大写字母和下划线命名，例如 APP_PATH,const TRANSACTION_TYPE = 'income', define('CURRENT_SCRIPT', 'index.php')。
配置参数以小写字母和下划线命名，例如 $config=array('url_route_on'=>true,'url_convert'=>array())。

详情参考：
https://psr.phphub.org/
https://github.com/summerblue/psr.phphub.org/tree/master/psrs
https://www.kancloud.cn/manual/thinkphp5/118007
http://www.cfei.net/archives/51594

 

======================================================================================
====================================Java编码规范==========================================
======================================================================================

变量标识符
1. 成员变量、局部变量使用lowerCamelCase风格（小驼峰法，首字母小写），如：inputUserId。
2. 变量命名不能以下划线或美元符号开始，也不能以下划线或美元符号结束。
3. 严禁使用拼音和英文混合的方式，更不允许直接使用中文的方式来命名。纯拼音命名方式也要避免使用，但国际通用的名称可视同英文，如：taobao, alibaba,xiamen等。

包
1. 包名统一用小写，点分符号之间有且仅有一个自然语义的英语单词。包名统一使用单数形式，但类名如有复数含义，类名可以用复数形式。如：com.alibaba.open.util.MessageUtils。

类
1. 类名使用UpperCamelCase风格（大驼峰法，首字母大写），如：XmlService, TcpUdpDeal, TaPromotion。
2. 抽象类命名使用Abstract或Base开头。
3. 如果使用到了设计模式，建议在类名中体现出具体的模式，有利于阅读者快速理解架构设计思想，如：public class OrderFactory; public class LoginProxy; public class ResourceObserver。
4. 对于Service和DAO类，基于SOA的理念，暴露出来的服务一定是接口，内部的实现类用Impl的后缀与接口区别，如：CacheServiceImpl实现CacheService接口。

枚举 (Enum)
1. 枚举类名建议带上Enum后缀，如：DealStatusEnum。
2. 枚举成员名称需要全大写，单词间用下划线隔开。（枚举其实就是特殊的常量类，且构造方法被默认强制是私有）如：UNKNOW_REASON。

参数
1. 参数名使用lowerCamelCase风格（小驼峰法，首字母小写），如：localValue。

方法
1. 方法名使用lowerCamelCase风格（小驼峰法，首字母小写），如：getHttpMessage()。

常量 (const)
1. 常量命名全部大写，单词间用下划线隔开，力求语义表达完整清楚，不要嫌名字长。如：MAX_SOCKET_COUNT。
2. long或者Long初始赋值时，必须使用大写的L，不能是小写的l，小写容易跟数字1混淆，造成误解。如：Long a = 2l; 很难辨别写的是数字的21还是Long型的2。

异常类
1. 异常类命名使用Exception结尾。

测试类
1. 测试类命名要以它要测试的类的名称开始，以Test结尾。

数组
1. 数组定义使用String[] args，不要使用String args[]的方式来定义。

POJO类
1. 布尔值的变量，都不要以加is前缀，否则部分框架解析会引起序列化错误，如：定义为基本数据类型boolean isSuccess的属性，它的方法也是isSuccess()，PRC框架在反向解析的时候，以为对应的属性名称是success，导致属性获取不到，进而抛出异常。

各层命名规约：
A) Service/DAO 层方法命名规约
1） 获取单个对象的方法用 get 做前缀。
2） 获取多个对象的方法用 list 做前缀。
3） 获取统计值的方法用 count 做前缀。
4） 插入的方法用 save（推荐）或 insert 做前缀。
5） 删除的方法用 remove（推荐）或 delete 做前缀。
6） 修改的方法用 update 做前缀。
B) 领域模型命名规约
1） 数据对象：xxxDO，xxx 即为数据表名。
2） 数据传输对象：xxxDTO，xxx 为业务领域相关的名称。
3） 展示对象：xxxVO，xxx 一般为网页名称。
4） POJO 是 DO/DTO/BO/VO 的统称，禁止命名成 xxxPOJO。

注释规约：
1. 代码修改的同时，注释也要进行相应的修改，尤其是参数、返回值、异常、核心逻辑等的修改。代码与注释更新不同步，就像路网与导航软件更新不同步一样，如果导航软件严重滞后， 就失去了导航的意义。其实一些优秀的团队在编写代码时默认是没有任何注释的，因为我们追求的是 self-explanatory methods。即代码本身已经就能说明它的用途。只有在很少的情况下需要添加注释。
2. 注释掉的代码尽量要配合说明，而不是简单的注释掉。 （代码被注释掉有两种可能性：1）后续会恢复此段代码逻辑。2）永久不用。前者如果没有备注信息，难以知晓注释动机。后者建议直接删掉（代码仓库保存了历史代码））

其他规约：
1. 循环体内，字符串的联接方式，使用 StringBuilder 的 append 方法进行扩展。（反编译出的字节码文件显示每次循环都会new出一个StringBuilder对象，然后进行append操作，最后通过toString方法返回String对象，造成内存资源浪费）
2. 相同参数类型，相同业务含义，才可以使用Java的可变参数，避免使用Object。如：public User getUsers(String type, Integer... ids)。（尽量不用可变参数编程）
3. 类成员与方法访问控制从严，要严控类、方法、参数、变量的访问范围。过宽泛的访问范围不利于模块解耦。思考：如果是一个 private 的方法，想删除就删除，可是一个 public 的 Service 方法，或者一个 public 的成员变量，删除一下，不得手心冒点汗吗？变量像自己的小孩，尽量在自己的视线内，变量作用域太大，会无限制的到处跑，那么你会担心的。
4. 接口类中的方法和属性不要加任何修饰符号(public也不要加)，保持代码的整洁性，并加上有效的Javadoc注释。尽量不要在接口中定义变量，如果一定要定义变量，肯定是与接口方法相关，并且是整个应用的基础常量，如：String COMPANY="alibaba";
5. 不要使用一个常量类维护所以常量，应该按常量功能进行归类，分开维护。如：缓存相关的常量放在类：CacheConsts下，系统配置相关的常量放在类：ConfigConsts下。大而全的常量类，非得使用查找功能才能定位到修改的常量，不利于理解和维护。
6. 对外暴露的接口签名，原则上不允许修改方法签名，避免对接口调用方产生影响。接口过时必须加@Deprecated注解，并清晰地说明采用的新接口或者新服务是什么。同理，不要使用过时的类或方法。
7. 所有的相同类型的包装类对象之间值的比较，全部使用equals方法比较。如：对于Integer var=?在-128至127之间的赋值，Integer对象是在IntegerCache.cache产生，会复用已有对象，这个区间内的Integer值可以直接使用==进行判断，但是这个区间之外的所有数据，都会在堆上产生，并不会复用已有对象，这是一个大坑，推荐使用equals方法进行判断。
8. 关于基本数据类型与包装数据类型的使用标准如下：
1） 所有的POJO类属性必须使用包装数据类型。
2） RPC方法的返回值和参数必须使用包装数据类型。
3） 所有的局部变量【推荐】使用基本数据类型。
9. 序列化类新增属性时，请不要修改serialVersionUID字段，避免反序列失败；如果完全不兼容升级，避免反序列化混乱，那么请修改serialVersionUID值。 因为serialVersionUID不一致会抛出序列化运行时异常。
10. 类内方法定义顺序依次是：公有方法或保护方法 > 私有方法 > getter/setter方法。说明：公有方法是类的调用者和维护者最关心的方法，首屏展示最好；保护方法虽然只是子类关心，也可能是“模板设计模式”下的核心方法；而私有方法外部一般不需要特别关心，是一个黑盒实现；因为方法信息价值较低，所有Service和DAO的getter/setter方法放在类体最后。
11. setter方法中，参数名称与类成员变量名称一致，this.成员名=参数名。在getter/setter方法中，尽量不要增加业务逻辑，增加排查问题的难度。
12. final可提高程序响应效率，声明成final的情况：
1） 不需要重新赋值的变量，包括类属性、局部变量。
2） 对象参数前加final，表示不允许修改引用的指向。
3） 类方法确定不允许被重写。
13. 不要在foreach循环里进行元素的remove/add操作。remove元素请使用Iterator方式，如果并发操作，需要对Iterator对象加锁。
14. 使用entrySet遍历Map类集合KV，而不是keySet方式进行遍历。（keySet其实是遍历了2次，一次是转为Iterator对象，另一次是从hashMap中取出key所对应的value。而entrySet只是遍历了一次就把key和value都放到了entry中，效率更高。如果是JDK8，使用Map.foreach方法）
15. 循环体中的语句要考量性能，以下操作尽量移至循环体外处理，如定义对象、变量、获取数据库连接，进行不必要的try-catch操作（这个try-catch是否可以移至循环体外）。
16. HashMap在容量不够进行resize时由于高并发可能出现死链，导致CPU飙升，在开发过程中注意规避此风险。

详情参考：

https://yq.aliyun.com/articles/69327

 

======================================================================================
====================================C#编码规范=======================================
======================================================================================

变量标识符
1. 变量建议置于块的开始处，不要总是在第一次使用它们的地方做声明。如：void MyMethod(){int int1 = 0; if (condition){int int2 = 0; ...}}
2. 只要合适，在变量名的末尾或开头加计算限定符（Avg、Sum、Min、Max、Index）。如：salaryAvg
3. 布尔变量名应该包含 Is，这意味着 Yes/No 或 True/False 值，如 fileIsFound。
3. 在命名状态变量时，避免使用诸如 Flag 的术语。状态变量不同于布尔变量的地方是它可以具有两个以上的可能值。不要使用 documentFlag，而是使用更具描述性的名称，如 documentFormatType。
4. 即使对于可能仅出现在几个代码行中的生存期很短的变量，仍然使用有意义的名称。仅对于短循环索引使用单字母变量名，如 i 或 j。
5. 尽量不要使用原义数字或原义字符串（避免使用不易理解的数字，用有意义的标识来替代（枚举和常量）），如For i = 1 To 7。而是使用命名常数，如 For i = 1 To NUM_DAYS_IN_WEEK 以便于维护和理解。
6. 不要将缩写或缩略形式用作标识符名称的组成部分。例如，使用 GetWindow，而不要使用 GetWin。

命名空间
1. 命名空间使用Pascal大小写(大驼峰法，首字母大写)，用逗号分隔开。
2. 命名命名空间时的一般性规则是使用公司名称，后跟技术名称和可选的功能与设计，如：CompanyName.TechnologyName[.Feature][.Design]，其中TechnologyName 指的是该项目的英文缩写，或软件名。
3. 命名空间和类不能使用同样的名字。例如，有一个类被命名为Debug后，就不要再使用Debug作为一个名称空间名。

类
1. 使用Pascal大小写(大驼峰法，首字母大写)，用名词或名词短语命名类，不要使用下划线字符 (_)。
2. 使用全称避免缩写，除非缩写已是一种公认的约定，如URL、HTML

特性 (Attribute，相当于Java的注解[Annotation])：
1. 应该总是将后缀 Attribute 添加到自定义属性类。如：public class ObsoleteAttribute {}

枚举 (Enum)
1. 对于 Enum 类型和值名称使用 Pascal 大小写，少用缩写。
2. 不要在 Enum 类型名称上使用 Enum 后缀。
3. 对大多数 Enum 类型使用单数名称，但是对作为位域的 Enum 类型使用复数名称。

参数
1. 使用描述性参数名称。参数名称应当对参数的含义具有足够的描述性，以便参数的名称及其类型可用于在大多数情况下确定它的含义。
2. 对参数名称使用 Camel 大小写（小驼峰法，首字母小写）。
3. 不要给参数名称加匈牙利语类型表示法的前缀。（匈牙利命名法：变量名＝属性＋类型＋对象描述，如：m_bFlag，m表示成员变量，b表示布尔，合起来为：“某个类的成员变量，布尔型，是一个状态标志”）

方法
1. 使用 Pascal 大小写，使用动词或动词短语命名方法，如：RemoveAll();GetCharArray();

属性 (property)
1. 使用 Pascal 大小写。使用名词或名词短语命名属性。
2. 不要使用匈牙利语表示法。
3. 考虑用与属性的基础类型相同的名称创建属性。例如，如果声明名为 Color 的属性，则属性的类型同样应该是 Color，如：public Color Color { get; set; }。

常量 (const)
1. 所有单词大写，多个单词之间用 "_" 隔开。 如：public const string PAGE_TITLE = "Welcome";

字段
1. private、protected 使用 Camel 大小写（小驼峰法，首字母小写）。如：protected string userName;
2. public 使用 Pascal 大小写（大驼峰法，首字母大写）。如：public string UserName;
3. 拼写出字段名称中使用的所有单词。仅在开发人员一般都能理解时使用缩写。字段名称不要使用大写字母。如：class SampleClass{string destinationUrl;}
4. 不要对字段名使用匈牙利语表示法。好的名称描述语义，而非类型。
5. 对预定义对象实例使用公共静态只读字段。如果存在对象的预定义实例，则将它们声明为对象本身的公共静态只读字段。使用 Pascal 大小写，原因是字段是公共的。如：public struct Color { public static readonly Color Red = new Color(0x0000FF); }

静态字段
1. 使用 Pascal 大小写。使用名词、名词短语或者名词的缩写命名静态字段。
2. 对静态字段名称使用匈牙利语表示法前缀。
3. 建议尽可能使用静态属性而不是公共静态字段。

事件
1. 对事件处理程序名称使用 EventHandler 后缀，如：ButtonClickEventHandler(object sender, EventArgs e)。
2. 指定两个名为 sender 和 e 的参数。sender 参数表示引发事件的对象。sender 参数始终是object 类型的，即使在可以使用更为特定的类型时也如此。与事件相关联的状态封装在名为 e 的事件类的实例中。对 e 参数类型使用适当而特定的事件类。
3. 用 EventArgs 后缀命名事件参数类。如：MySelfEventArgs:EventArgs {}
4. 考虑用动词命名事件。如：class PublishEvent {}
5. 使用动名词（动词的“ing”形式）创建表示事件前的概念的事件名称，用过去式表示事件后。例如，可以取消的 Close 事件应当具有 Closing 事件和 Closed 事件。不要使用BeforeXxx/AfterXxx 命名模式。
6. 不要在类型的事件声明上使用前缀或者后缀。例如，使用 Close，而不要使用 OnClose。
7. 通常情况下，对于可以在派生类中重写的事件，应在类型上提供一个受保护的方法（称为OnXxx）。此方法只应具有事件参数 e，因为发送方总是类型的实例。

异常
1. 使用 Pascal 大小写。使用名词或名词短语命名异常，并且在类名中能清楚的描述出该异常的原因。以Exception结尾。如：class FileNotFoundException {}

委托
1. 应该总是将后缀 EventHandler 添加到委托类。如：public delegate void MouseEventHandler (object sender, MouseEventArgs e);

控制语句
1. return语句中不使用括号，除非它能使返回值更加清晰。如：return; return myDisk.size(); return (size ? size : defaultSize);

详情参考：
http://www.cnblogs.com/jailu/archive/2007/07/17/820959.html
http://www.studyofnet.com/news/211.html

 

======================================================================================
====================================代码外观规范======================================
======================================================================================

1. 列宽: 代码列宽控制在110或120字符左右，超出需要换行。
2. 换行: 当表达式超出或即将超出规定的列宽，遵循以下规则进行换行
    1). 第二行相对第一行缩进 4 个空格，从第三行开始，不再继续缩进
    2). 在逗号后换行。
    3). 在操作符前换行，运算符与下文一起换行，方法调用的点符号与下文一起换行。
    4). 在括号前不要换行
    当以上规则会导致代码混乱的时候自己采取更灵活的换行规则。
    可以通过一些重构手法来减少单行字符长度从而避免换行。关于参数，很多方法调用超过 120 个字符需要换行，这暴露除了过长参数列的代码坏味道，解决方式之一就是使用重构手法的 Replace Parameter With Method 的方式把一次方法调用化为多次方法调用，或者使用 Introduce Parameter Object 手法创造出参数对象并进行传递。
3. 缩进: 缩进采用4个空格，禁止使用tab字符。使用空格代替tab字符进行缩进已经成为了编程界的共识。其主要原因是不同的平台甚至不同的编辑器下tab字符的长短是不一样的。
4. 空格: 多个参数用逗号隔开，每个逗号后都应加一个空格。
5. 声明：一行只建议作一个声明，声明必需加注释说明，并从上到下依次按字母顺序排列。如
    int level; //推荐
    int x, y; //不推荐
6. 杜绝不规范的缩写，避免望文不知义，如：AbstractClass缩写成AbsClass，此类随意缩写将严重降低代码的可阅读性。

 

======================================================================================
====================================数据库设计约定=======================================
======================================================================================

 

数据表和字段
1. 库名与应用名称尽量一致，使用小写英文和下划线组成。（从数据库名称中可以一眼看出是哪个应用或者系统在使用的）
2. 数据表和字段采用小写字母或数字加下划线方式命名，并注意字段名不要以下划线或数字开头，例如 user 表和 user_name字段，不建议使用驼峰和中文作为数据表字段命名。（数据库字段名的修改代价很大，因为无法进行预发布，所以字段名称需要慎重考虑）
3. 数据表不使用复数名词。（表名应该仅仅表示表里面的实体内容，不应该表示实体数量，对应于模型类名也是单数形式，符合表达习惯）
4. 表的命名最好是加上“业务名称_表的作用”。 正例：tiger_task / tiger_reader / mpp_config。
5. 唯一索引名为uk_字段名；普通索引名则为idx_字段名。（uk_ 即 unique key；idx_ 即index的简称）
6. 小数类型为decimal，禁止使用float和double。（float和double在存储的时候，存在精度损失的问题，很可能在值的比较时，得到不正确的结果。如果存储的数据范围超过decimal的范围，建议将数据拆成整数和小数分开存储）
7. 如果存储的字符串长度几乎相等，使用char定长字符串类型。
8. varchar是可变长字符串，不预先分配存储空间，长度不要超过5000，如果存储长度大于此值，定义字段类型为text，独立出来一张表，用主键来对应，避免影响其它字段索引效率。
9. 表必备三字段：id, created_at, modified_at（或create_time,update_time）。 说明：其中id必为主键，类型为unsigned bigint、单表时自增、步长为1。created_at, modified_at的类型均为date_time类型。
10. 如果修改字段含义或对字段表示的状态追加时，需要及时更新字段注释。
11. 字段允许适当冗余，以提高性能，但是必须考虑数据同步的情况。冗余字段应遵循：
1）不是频繁修改的字段。
2）不是varchar超长字段，更不能是text字段。
例如：商品类目名称使用频率高，字段长度短，名称基本一成不变，可在相关联的表中冗余存储类目名称，避免关联查询。
12. 单表行数超过500万行或者单表容量超过2GB，才推荐进行分库分表。 说明：如果预计三年后的数据量根本达不到这个级别，请不要在创建表时就分库分表。
13. 合适的字符存储长度，不但节约数据库表空间、节约索引存储，更重要的是提升检索速度。 如：人的年龄用unsigned tinyint（表示范围0-255，人的寿命不会超过255岁）；海龟就必须是smallint，但如果是太阳的年龄，就必须是int；如果是所有恒星的年龄都加起来，那么就必须使用bigint。
14. 尽量使用数字型字段，若只含数值信息的字段尽量不要设计为字符型，这会降低查询和连接的性能，并会增加存储开销。这是因为引擎在处理查询和连 接时会逐个比较字符串中每一个字符，而对于数字型而言只需要比较一次就够了。（IP、时间可以转换成数值类型存储，日期保存为数值类型(unix时间戳)，可以提高范围查询效率，国际化兼容性较好；IP保存为数值类型，可以提高范围查询效率；中文以Base64编码保存，这样在MySql多种引擎编码下兼容性较好）
15. 最好不要给数据库留NULL，尽可能的使用 NOT NULL填充数据库.（备注、描述、评论之类的可以设置为 NULL）。
16. 拆分大的 DELETE 或 INSERT 语句，如果你需要在一个在线的网站上去执行一个大的 DELETE 或 INSERT 查询，你需要非常小心，要避免你的操作让你的整个网站停止响应。因为这两个操作是会锁表的，表一锁住了，别的操作都进不来了。如果你有一个大的处理，你定你一定把其拆分，使用 LIMIT 条件是一个好的方法。下面是一个示例：DELETE FROM logs WHERE log_date <= '2017-07-11' LIMIT 1000。

 

索引规约：
1. 业务上具有唯一特性的字段，即使是组合字段，也必须建成唯一索引。（不要以为唯一索引影响了insert速度，这个速度损耗可以忽略，但提高查找速度是明显的；另外，即使在应用层做了非常完善的校验和控制，只要没有唯一索引，根据墨菲定律，必然有脏数据产生）
2. 超过三个表禁止join。需要join的字段，数据类型保持绝对一致；多表关联查询时，保证被关联的字段需要有索引。（即使双表join也要注意表索引、SQL性能）
3. 页面搜索严禁左模糊或者全模糊，如果需要请走搜索引擎来解决。（索引文件具有B-Tree的最左前缀匹配特性，如果左边的值未确定，那么无法使用此索引）
4. 建组合索引的时候，区分度最高的在最左边。 如：where a=? and b=? ，a列的几乎接近于唯一值，那么只需要单建idx_a索引即可。（存在非等号和等号混合判断条件时，在建索引时，请把等号条件的列前置。如：where a>? and b=? 那么即使a的区分度更高，也必须把b放在索引的最前列）
5. 如果有全球化需要，所有的字符存储与表示，均以utf-8编码，那么字符计数方法注意：SELECT LENGTH("轻松工作")；返回为12; SELECT CHARACTER_LENGTH("轻松工作")；返回为4。如果要使用表情，那么使用utfmb4来进行存储，注意它与utf-8编码的区别。
6. 使用索引是有代价的, 索引需要空间来存储,也需要定期维护, 每当有记录在表中增减或索引列被修改时, 索引本身也会被修改. 这意味着每条记录的INSERT , DELETE , UPDATE将为此多付出4 , 5 次的磁盘I/O （更新表时不仅需要保存数据，还要保存索引文件）. 因为索引需要额外的存储空间和处理,那些不必要的索引反而会使查询反应时间变慢.。定期的重构索引是有必要的。 
7. 对于唯一值的列，索引效果最好，对于具有多个重复值的列，如年龄或性别，建立索引不是好办法。
8. 索引不会包含有NULL值的列，在数据库设计时尽量不要让字段的默认值为NULL，否则无法建立相关字段的索引。

 

SQL命令优化规约：
1. 使用参数化查询：防止SQL注入，预编译SQL命令提高效率。
2. 去掉不必要的查询和搜索字段：其实在项目的实际应用中，很多查询条件是可有可无的，能从源头上避免的多余功能尽量砍掉，这是最简单粗暴的解决方案。
3. 选择最有效率的表名顺序: 数据库的解析器按照从右到左的顺序处理FROM子句中的表名，FROM子句中写在最后的表将被最先处理，在FROM子句中包含多个表的情况下,你必须选择记录条数最少的表放在最后，如果有3个以上的表连接查询,那就需要选择那个被其他表所引用的表放在最后。
4. 不要使用select *：不要使用select *，以提高查询效率，减少输出的数据量，提高传输速度。（数据库或在解析过程中将"*"依次转换成所有列名，这意味着消耗更多的时间）
5. 尽量避免向客户端返回大数据量，若数据量过大，应该考虑相应需求是否合理。
6. 减少访问数据库的次数：通过存储过程等，把多条语句放在一个存储过程中执行，减少数据库访问次数。
7. 使用表的别名(Alias)：当在SQL语句中连接多个表时, 请使用表的别名并把别名前缀于每个Column上.这样一来,就可以减少解析的时间并减少那些由Column歧义引起的语法错误。
8. 使用列的别名：当列的名称很长的时候，使用简短的列的别名可以查询结果更清晰，更简洁。
9. 统计相关的查询，影响结果集往往巨大，应避免在业务高峰期执行统计相关的查询，或者仅在从库中执行统计查询。同时建议把数据先保存在内存、缓存中(如redis)，再按一定策略写入数据库。
10. select count(*) from table；这样不带任何条件的count会引起全表扫描，并且没有任何业务意义，是一定要杜绝的，可以用其他方法代替。
11. where 子句中对字段进行 null 值判断、包含not、!=、<>等操作符，或like的关键词前加%(like '%关键词')，都无法使用索引，从而引发全表扫描。
12. 使用like进行模糊查询时应注意,除非必要，否则不要在关键词前加%，否则必然导致全表查询。
13. 对于多张大数据量（这里几百条就算大了）的表JOIN，要先分页再JOIN，否则逻辑读会很高，性能很差。
14. 避免频繁创建和删除临时表，以减少系统表资源的消耗。
15. 如果使用到了临时表，在存储过程的最后务必将所有的临时表显式删除，先 truncate table ，然后 drop table ，这样可以避免系统表的较长时间锁定。

 

 

第二节：网站安全的应用（安全规范）
1. 不要将系统级别的错误直接暴露给用户，而更应该的是把系统抛出的错误信息记录到LOG日志文件中去，告诉用户友好的提示信息。
2. 不管客户端是否做过数据校验，在服务端必须要有数据校验
    1). 对用户输入的字符串值进行长度验证（脚本注入攻击必然会大大增加变量值的长度，通过长度验证可以有效避免注入攻击）
    2). 对接收的参数进行类型格式化，比如id参数获取后，进行int类型转换
    3). 对用户输入的值进行html编码（防御xss跨站攻击）
    4). 对用户输入的字符串值包含的单引号、双引号等符号进行转义（防御SQL注入攻击）
    5). 对接收的参数内容，去掉任何远程内容的引用（尤其是样式表和javascript）
3. 页面输出之前做html转码，不要原内容输出。（防御xss跨站攻击）
4. 不要把机密的信息明文存储，务必进行加密。（这样就算信息被窃取，也不会造成很大损失）
5. 尽量使用cookie的httponly属性，使客户端js脚本无法读取cooie；对cookie内容进行加密。（防御xss跨站攻击-Cookie欺骗）
6. 必须使用参数化SQL命令，永远不要使用动态拼装的SQL命令。（防御SQL注入攻击）
7. 实现session tokens表单令牌，拒绝不明来源的非法提交。
8. 对用户上传的文件尽心更严格限制，例如限制文件类型、文件尺寸等。同时对上传文件后存储的文件目录进行权限限制，去掉脚本执行权限和文件解压权限等。（防御上传入侵）
9. 不要直接暴露文件下载地址，而要把文件下载放到一个逻辑处理程序中，并对每个IP做刷新次数的限制。（防御CC攻击直接通过刷新文件下载而耗尽流量）
10. 页面尽可能把页面做成静态，因为动态网页相对静态网页，对CPU、IO、数据库的性能消耗高很多，做成静态网页可以节约服务器资源，提高服务器性能。（防御DDoS攻击、防御xss攻击和SQL注入攻击）
11. 检查程序漏洞，对程序引用的第三方代码、第三方插件、第三方类库等，要即时更新官方漏洞补丁。
12. 服务器帐号、Ftp帐号、数据库帐号、网站管理员帐号等，要设置足够安全的强度，密码最好不少于12位，并包含大小写字母、数字、特殊字符等。（防御暴力破解攻击）
13. 过滤不必要的端口和服务，可以使用Inexpress、Express、Forwarding等工具来过滤不必要的服务和端口。（防御端口入侵和DDoS端口攻击）
14. 在存在多站的服务器上，严格限制每一个站允许的IP连接数和CPU使用时间。（防御DDoS攻击）
15. 对网站启用https协议，防止数据被窃听，特别是在交易过程中，使用https保证数据传输安全。

参考文章：

http://www.cnblogs.com/sochishun/p/7007959.html
http://www.cnblogs.com/sochishun/p/7081739.html
http://www.cnblogs.com/sochishun/p/7028056.html
http://www.cnblogs.com/sochishun/p/6994918.html
http://www.cnblogs.com/sochishun/p/6993997.html

网站安全工具/漏洞检测工具
在线检测：
360网站安全检测 - 在线安全检测，网站漏洞修复，网站后门检测。 (http://webscan.360.cn/)
腾讯电脑管家官方网站网站安全检测专区 ，提供网址安全检测,网站安全检测诊断工具,域名检测等。 (http://guanjia.qq.com/online_server/webindex.html)
百度云观测 - 百度旗下网站云监测平台|免费安全检测|网站测速|漏洞扫描|网站检测。 (http://ce.baidu.com/)
网站安全检测为站长免费提供了网站漏洞检测、网站挂马实时监控、网站篡改实时监控等服务。 (http://tool.chinaz.com/webscan/)

参考文章：
http://tool.chinaz.com/webdetect/
http://www.2cto.com/article/201609/551091.html

 

第三节：前端优化约定
 

前端优化：
1. 尽量减少HTTP请求：把多个css文件合并成一个。
2. 使用Minify压缩精简Javascript和Css代码文件。
3. 把CSS文件放到HTML代码页面头部，这么做可以避免浏览器在解释一次之后，使用css进行第二次解释，因为用户对css裸奔的效果根本就不感兴趣。
4. 避免 CSS 表达式，凡是只有IE能用的东西，都不是好东西。
5. 从页面中剥离 JavaScript 与 CSS放到外部文件中引用，剥离后，能够有针对性的对其进行单独的处理策略，比如压缩或者缓存策略。
6. 使用 <link> 而不是 @import，在 IE 中 @import 指令等同于把 link 标记写在 HTML 的底部，这与第一条相违背。
7. JS尽量放到页面最下端，当一个脚本在下载的时候，浏览器会卡住，无法响应其他请求。所以，可以将功能性的JS放到最后端去处理。
8. 如果是移动端，单个数据对象小于25KB。
9. 注意控制Cookie大小和污染，因为Cookie是本地的磁盘文件，每次浏览器都会去读取相应的Cookie，所以建议去除不必要的Coockie，使Coockie体积尽量小以减少对用户响应的影响。

 

图片优化：
1. 压缩图片并使用 CSS Sprites 对图片优化，简单的说就是"利用 CSS background 相关元素进行背景图绝对定位"，把多次HTTP 调用变为一次调用，减少HTTP请求。
2. 尽可能的使用 PNG 格式的图片，因为和GIF相比，PNG有更多的功能和更小的体积。
3. 用更小的并且可缓存的 favicon.ico，原因是没有favicon.ico，服务器会返回一个404，与可以长时间缓存的文件相比，大量的404会增加服务器的响应数量。

 

服务端优化：

1. 使用CDN加速，静态资源做CDN部署。（使用前端CDN增加网页的并行载入速度，减少本地服务器的负担，节省流量。一个浏览器对与同一域名的并行下载的个数（浏览器并发请求数）是有限的，一般不超过10个。这样，我们可以使用不同的域名来提升下载的速度）
2. 开启静态文件压缩，使用Gzip压缩内容，以减少宽带需求，让页面更快加载出来。
3. 对Ajax请求使用GET方法，XMLHttpRequest POST 要两步，而 GET 只需要一步。
4. 尽量使用JSON格式来进行数据交换。（与XML序列化相比，JSON序列化后产生的数据一般要比XML序列化后数据体积小）
5. 前后端做数据分离，让搜索服务解耦，在高并发情况下更灵活做负载均衡。（前端使用Vue.js、AngularJs等，数据来源可以不限编程语言）
6. 后端数据大部分来自缓存，加载快，给用户更快的体验。（商品详情、商品库存等，可以放在缓存（redis集群），避免频繁去数据库取数据，提高商品信息的读能力）

参考文章：
http://www.cnblogs.com/sochishun/p/7071705.html
http://www.cnblogs.com/sochishun/p/7003190.html
http://www.open-open.com/news/view/9902b7
http://www.cnblogs.com/Darren_code/archive/2011/12/31/property.html
http://www.cnblogs.com/wildweeds/archive/2010/06/12/web_performance.html
http://www.cnblogs.com/JustinYoung/archive/2007/11/20/speeding-up-web-site-14rule.html
http://www.cnblogs.com/zhangpengshou/archive/2013/05/31/3110304.html

 

前端性能检测工具：
浏览器插件

Google Page Speed: 谷歌网页速度测试是一个开源的Firefox / Firebug插件。 网站管理员和Web开发人员可以使用该工具来评估其网页的性能并获取有关如何改进它们的建议。

YSlow: YSlow用来分析网页性能，并在高性能网页规则基础上建议如何改善。

PageTest: Internet Explorer的插件，常用来显示浏览器加载内容时发出的请求并提供了该进页面性能的建议。

Pylot: 开源的测试工具，可以测试网站的性能和可扩展性。 它运行HTTP负载测试，这是有用的容量规划，基准，分析和系统调整。

在线测试网站

Pingdom: 测试网站所有对象的加载时间（HTML，images，JavaScript，CSS，嵌入式框架等）。 您还可以检查网站每个元素的加载速度并改善加载缓慢的项目。 在测试结果中，可以看到网站每个元素的加载时间报告，元素的大小和元素的总数量。
测试地址：https://www.pingdom.com/

GTmetrix: 结合了最流行的Firefox性能组件YSlow的和谷歌网页速度测试工具。 Gtmetrix给你提供改进网站速度的建议，虽然YSlow的和谷歌网页的速度测试的建议是针对Firefox的，也可以适用于其他浏览器。
测试地址：https://gtmetrix.com/

Site-Perf: 它模拟浏览器下载图片，CSS，JS和其他文件，在报告中你可以看到先加载网站的哪些页以及加载时间。 这是十分有用的性能报告，可以用来查找到提高你的网站的载入速度需要改善的元素。
测试地址：https://gtmetrix.com/

参考文章：
http://www.cnblogs.com/lhb25/archive/2010/12/26/1917047.html

 
第四节：代码维护约定
 

1. 对外暴露的接口签名，原则上不允许修改方法签名，避免对接口调用方产生影响。接口过时必须加@Deprecated注解，并清晰地说明采用的新接口或者新服务是什么。同理，不要使用过时的类或方法。
2. 代码修改的同时，注释也要进行相应的修改，尤其是参数、返回值、异常、核心逻辑等的修改。代码与注释更新不同步，就像路网与导航软件更新不同步一样，如果导航软件严重滞后， 就失去了导航的意义。其实一些优秀的团队在编写代码时默认是没有任何注释的，因为我们追求的是 self-explanatory methods。即代码本身已经就能说明它的用途。只有在很少的情况下需要添加注释。
3. 注释掉的代码尽量要配合说明，而不是简单的注释掉。 代码被注释掉有两种可能性：
1）后续会恢复此段代码逻辑。
2）永久不用。
前者如果没有备注信息，难以知晓注释动机。后者建议直接删掉。（代码仓库保存了历史代码）
4. 代码修改后，要做功能测试，确保没有因为修改而产生新的BUG。

参考文章：
http://blog.sina.com.cn/s/blog_7665a8ef0100rj6w.html
http://www.cnblogs.com/houbowei/archive/2010/06/07/1752821.html

 
第五节：产品发布约定
 

1. 项目经理编写产品发布说明，产品发布说明的内容应该包括：产品发布时间；产品版本说明；产品概要介绍；本次发布包含的安装包、文档说明；本次发布包含或者新增的功能特性说明；遗留问题及影响说明；版权声明以及其他需要说明的事项。
2. 发布之前，所有程序由测试人员进行确认测试；检查登记的所有bug都已关闭，或者遗留的bug不影响系统的使用，如果有严重bug未解决（级别为很严重以上）不能发布。 
3. 测试负责人编写release产品测试报告和总结，给出发布与否的结论。
4. 软件打好包后邮件通知相关人员，提交产品安装包。 
5. 源码、文档入基线库。源码包括数据库创建脚本（含静态数据）、 编译构建脚本和所有源代码；文档包括需求、设计、测试文档，安装手册、使用手册、二次开发手册、产品介绍（ppt）、使用demo和项目经理提交的产品发布说明等。
6. 上传程序包、使用文档至download站点。
7. 项目经理或者高级经理发送产品正式发布通知邮件，通知开发、测试、市场、销售各相关部门并附上产品发布说明和产品介绍；或者以产品发布会议的形式进行通知。
8. 产品发布后，在使用过程中可能还会发现一些bug。在不影响正常使用的情况下，这些bug将在下一版本发布时解决；如果bug严重影响使用，必须打patch或者按照流程重新发布。

参考文章：
https://wenku.baidu.com/view/6f9b17baf121dd36a32d82c0.html
http://www.blogjava.net/jasmine214--love/archive/2011/11/24/364733.html

 
第六节：源码提交规范
 

1. 先更新，再提交
源码托管更新的原则是要随时更新，随时提交。当完成了一个小功能，能够通过编译并且自己测试之后，谨慎地提交。
如果在修改的期间别人也更改了对应的文件，那么commit就可能会失败。如果别人和自 己更改的是同一个文件，那么update时会自动进行合并，如果修改的是同一行，那么合并时会产生冲突，这种情况就需要同之前的开发人员联系，两个人一起协商解决冲突，解决冲突之后，需要两人一起测试保证解决冲突之后，程序不会影响其他功能。
在更新时注意所更新文件的列表，如果提交过程中产生了更新，则也是需要重新编译并且完成自己的一些必要测试，再进行提交。这样既能了解别人修改了哪些文件，同时也能避免合并错误导致代码有错。

2. 多提交
每次提交的间歇尽可能地短，以几个小时的开发工作为宜。例如在更改UI界面的时候，可以每完成一个UI界面的修改或者设计，就提交一次。在开发功能模块的时候，可以每完成一个小细节功能的测试，就提交一次，在修改bug的时候，每修改掉一个bug并且确认修改了这个bug，也就提交一次。我们提倡多提交，也就能多为代码添加上保险。

3. 不要提交不能通过编译的代码
代码在提交之前，首先要确认自己能够在本地编译。如果在代码中使用了第三方类库，要考虑到项目组成员中有些成员可能没有安装相应的第三方类库。项目经理在准备项目工作区域的时候，需要考虑到这样的情况，确保开发小组成员在签出代码之后能够在统一的环境中进行编译。

4. 每次提交必须书写明晰的标注
在一个项目组中使用SVN，如果提交空的标注或者不确切的标注将会让项目组中其他的成员感到很无奈，项目经理无法很清晰的掌握工作进度，无法清晰的把握此次提交的概要信息。在发现错误后也无法准确的定位引起错误的文件。所以，在提交工作时，要填写明晰的标注，能够概要的描述所提交文件的信息，让项目组其他成员在看到标注后不用详细看代码就能了解你所做的修改。

5. 提交时注意不要提交本地自动生成的文件
例如eclipse中的.classpath文件，Windows生成的缩略图Thumbs.db，项目编译生成的临时文件.obj, .class等等。如果项目中没有进行这方面的配置来强行禁止提交这样的文件，请自觉不要提交这样的文件。提交了这样的文件后，别人在更新后就可能与本地的环境冲突从而影响大家的工作。

6. 不要提交自己不明白的代码
代码在提交入源码托管服务器之后，你的代码将被项目成员所分享。如果提交了你不明白的代码，你看不懂，别人也看不懂，如果在以后出现了问题将会成为项目质量的隐患。因此在引入任何第三方代码之前，确保你对这个代码有一个很清晰的了解。

7. 慎用锁定功能
在项目中要慎用锁定的功能，在你锁定了一个文件之后别人就无法继续修改提交该文件，虽然可以减少冲突的发生率，但是可能会影响项目组中其他人员的工作。平时只有在编辑那些无法合并的文件（例如图片文件，flash文件等）时，才适当的采用锁定操作。

参考文章：
http://www.cnblogs.com/xpxu/archive/2010/04/06/1705195.html
http://blog.csdn.net/nokianasty/article/details/12168577
http://www.360doc.com/content/12/0222/13/5236655_188606356.shtml
http://www.ruanyifeng.com/blog/2015/08/git-use-process.html

 

第七节：数据库防篡改设计
 

1. 使用合适的字符存储长度，防止被注入攻击的信息保存在数据库，造成永久的攻击和破坏。
2. 对机密的数据进行加密，如密码字段。
3. 对交易信息使用巧妙的隐藏手段进行冗余校验，比如新增一个交易校验表，表最好不要和主数据库放在一起，表结构为(id, sign)，id对应交易明细表的自增长id，sign包含交易明细表的交易金额、交易时间、交易用户、用于余额等进行des加密，这样如果用户账户信息被篡改，就可以通过后台做数据挖掘对比，筛选被篡改的记录。或者可以通过巧妙的方法，把sign的值变成交易单号，直接就可以和交易表无缝融合。
4. 定期做好数据备份，特别是重要的资金信息的备份，做好灾后恢复的准备。

参考文章：
http://www.cnblogs.com/huangzijian/p/6347293.html

 

第八节：数据备份规范

1. 备份数据，并认真做好备份记录（最好有专职人员负责数据备份）。
2. 必须做好两个或两个以上的备份副本，并将其分别存储于本地磁介质(指硬盘)与移动磁介质(指优盘)或网络服务器上，以备灾难恢复。
3. 定期检查备份数据的保存情况。
4. 根据数据的保密规定和用途，确定使用人员的存取权限、存取方式和审批手续，禁止泄露、更改和转移专业数据信息。
5. 备份数据类别包括：网站、邮件、数据库、系统文件、日志文件、配置文件、图片、视频、CA证书等。

参考文章：
https://wenku.baidu.com/view/f6282f2c0066f5335a8121f1.html
https://yq.aliyun.com/product/1229?utm_medium=text&utm_source=baidu&utm_campaign=dts&utm_content=se_460895
https://wenku.baidu.com/view/cbc2e438580216fc700afd40.html

 

第九节：第三方增值服务应用
第三方云主机提供商一般会提供安全增值服务，360公司也有提供网站安全检测服务，善用这些服务可以大大提高网站安全性。

参考文章：
http://webscan.360.cn/
http://ce.baidu.com/
http://guanjia.qq.com/online_server/webindex.html
http://tool.chinaz.com/webscan