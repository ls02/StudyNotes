[TOC]

# 🥚🥚🥚C++发展史

> C++是一种计算机高级程序设计语言，由[C语言](https://baike.baidu.com/item/C语言/105958)扩展升级而产生 ，最早于1979年由[本贾尼·斯特劳斯特卢普](https://baike.baidu.com/item/本贾尼·斯特劳斯特卢普/10613051)在AT&T贝尔工作室研发。
>
> C++既可以进行C语言的过程化[程序设计](https://baike.baidu.com/item/程序设计/223952)，又可以进行以抽象数据类型为特点的基于对象的程序设计，还可以进行以继承和多态为特点的面向对象的程序设计。C++擅长面向对象程序设计的同时，还可以进行基于过程的程序设计。
>
> C++拥有计算机运行的实用性特征，同时还致力于提高大规模程序的编程质量与程序设计语言的问题描述能力。

### 发展历程

> 1970年，AT&T贝尔实验室的工作人员D.Ritchie和K.Thompson共同研发了C语言。研制C语言的初衷是用它编写UNIX系统程序，因此，实际上C语言是UNIX的“副产品”。
>
> 1971年，瑞士联邦技术学院N.Wirth教授发明了第一个结构化的编程语言[Pascal](https://baike.baidu.com/item/Pascal/241171)。
>
> 20世纪70年代中期，本贾尼·斯特劳斯特卢普在剑桥大学计算机中心工作。斯特劳斯特卢普希望开发一个既要编程简单、正确可靠，又要运行高效、可移植的计算机程序设计语言。而以C语言为背景，以[Simula](https://baike.baidu.com/item/Simula/6913723)思想为基础的语言，正好符合斯特劳斯特卢普的初衷和设想。
>
> 1979年，本贾尼·斯特劳斯特卢普到了AT&T贝尔实验室，开始从事将C改良为带类的C（C with classes）的工作。、1983年，该语言被正式命名为C++。
>
> 1985年、1990年和1994年，C++先后进行3次主要修订。
>
> C++的标准化工作于1989年开始，并成立了一个[ANSI](https://baike.baidu.com/item/ANSI/10401940)和ISO（International Standards Organization）国际标准化组织的联合标准化委员会。
>
> 1994年1月25曰，联合标准化委员会提出了第一个标准化草案。在该草案中，委员会在保持斯特劳斯特卢普最初定义的所有特征的同时，还增加了部分新特征。
>
> 在完成C++标准化的第一个草案后不久，亚历山大·斯特潘诺夫（[Alexander Stepanov](https://baike.baidu.com/item/Alexander Stepanov/9703963)）创建了标准模板库（Standard Template Library，STL）。在通过了标准化第一个草案之后，联合标准化委员会投票并通过了将STL包含到C++标准中的提议。STL对C++的扩展超出了C++的最初定义范围。虽然在标准中增加STL是个很重要的决定，但也因此延缓了C++标准化的进程。
>
> 1997年11月14日，联合标准化委员会通过了该标准的最终草案，1998年，C++的ANSI/IS0标准被投入使用。

### 语言标准

> 自C++的ANSI/IS0标准投用以来，共进行过5次更新。

#### C++标准更新记录

| **标准版本** | **发布时间**  |    **正式名称**    |                         **更新内容**                         |
| :----------: | :-----------: | :----------------: | :----------------------------------------------------------: |
|    C++ 03    |    2003年     | ISO/IEC 14882:2003 |               对C++ 98版本的漏洞做了部分修改。               |
|    C++ 11    | 2011年8月12日 | ISO/IEC 14882:2011 | 对容器类的方法做了三项主要修改：1、新增了右值引用，可以给容器提供移动语义。2、新增了模板类initilizer_list，因此可将initilizer_list作为参数的构造函数和赋值运算符。3、新增了可变参数模板（variadic template）和函数参数包（parameter pack），可以提供就地创建（emplacement）方法。 |
|    C++ 14    | 2014年8月18日 | ISO/IEC 14882:2014 | C++11的增量更新。主要是支持普通函数的返回类型推演，泛型lambda，扩展的lambda捕获，对constexpr函数限制的修订，constexpr变量模板化等。 |
|    C++ 17    | 2017年12月6日 | ISO/IEC 14882:2017 | 新增UTF-8 字符文字、折叠表达式（fold expressions）：用于可变的模板、内联变量（inline variables）：允许在头文件中定义变量；在if和switch语句内可以初始化变量；结构化绑定（Structured Binding）：for（auto [key,value] : my_map）{…}；类模板参数规约（Class Template Argument Deduction）：用pair p{1, 2.0}; 替代pair{1, 2.0};；&gt;；static_assert的文本信息可选；删除trigraphs；在模板参数中允许使用typename（作为替代类）；来自 braced-init-list 的新规则用于自动推导；嵌套命名空间的定义；允许命名空间和枚举器的属性；新的标准属性：[[fallthrough]], [[maybe_unused]] 和 [[nodiscard]]；对所有非类型模板参数进行常量评估；Fold表达式，用于可变的模板；A compile-time static if with the form if constexpr（expression）；结构化的绑定声明，允许auto [a, b]=getTwoReturnValues（）。 |
|    C++ 20    | 2020年12月7日 | ISO/IEC 14882:2020 | 新增模块（Modules）、协程（Coroutines）、范围 （Ranges）、概念与约束 （Constraints and concepts）、指定初始化 (designated initializers）、操作符“<=> != ==”；constexpr支持：new/delete、dynamic_cast、try/catch、虚拟、constexpr向量和字符串；计时：日历、时区支持。 |

# 🧂🧂🧂C++关键字

> 关键字（*keyword*）是整个语言范围内预先保留的标识符，每个C++关键字都有特殊的含义。经过预处理后，关键字从预处理记号（*preprocessing-token*）中区出来，剩下的标识符作为记号（*token*），用于声明对象、函数、类型、命名空间等。不能声明与关键字同名的标识符。
>
> 各个版本的ISO C++都规定以下划线接大写字母起始的标识符保留给实现。编译器可以用这些保留标识符作为扩展关键字，这不保证可移植性。以下讨论ISO C++所保留的关键字。

**ISO C++ 98关键字共63个，按标准排版如下：**

|    asm     |        do        |    if     |   return    | typedef  |
| :--------: | :--------------: | :-------: | :---------: | :------: |
|    auto    |      double      |  inline   |    short    |  typeid  |
|    bool    |   dynamic_cast   |    int    |   signed    | typename |
|   break    |       else       |   long    |   sizeof    |  union   |
|    case    |       enum       |  mutable  |   static    | unsigned |
|   catch    |     explicit     | namespace | static_cast |  using   |
|    char    |      export      |    new    |   struct    | virtual  |
|   class    |      extern      | operator  |   switch    |   void   |
|   const    |      false       |  private  |  template   | volatile |
| const_cast |      float       | protected |    this     | wchar_t  |
|  continue  |       for        |  public   |    throw    |  while   |
|  default   |      friend      | register  |    true     |  delete  |
|    goto    | reinterpret_cast |    try    |             |          |

# 🍿🍿🍿命名空间域

### 什么是命名空间域？

> 命名空间域就是一个独立的空间外面不能直接调用该空间域只能用访问限定符指定访问该空间域。

#### 命名空间域的意义

> 命名空间域主要是用来解决C语言里面命名冲突的问题，使用命名空间域单独开辟一个独立空间，当需要调用该域的函数时只需指定，而同一种名字的函数可以有多份不过需要放到不同的空间域内，这样才不会冲突。

### 命名空间域的创建

> 我们创建一个命名空间域时需要使用关键字`namespace`来创建一个空间域。
>
> **使用方法：** `namespace 空间名` {}
>
> **使用案列**
>
> ```cpp
> #include <iostream>
> 
> using namespace std;
> 
> namespace ls
> {
> 	int a = 30;//ls空间域
> }
> 
> int a = 100;//全局域
> 
> int main()
> {
> 	int a = 200;//局部域
> 
> 	cout << a << endl;//如果不指定空间域那么使用的是局部域，因为局部优先
> 	cout << ::a << endl;//指定空域是优先使用全局域
> 	cout << ls::a << endl;//指定使用某个空间域
> 
> 	return 0;
> }
> ```



### 域作用访问限定符

> 用于访问指定域的内容，用于访问指定域的符号叫做：**域作用限定符**
>
> **使用方法：** 域名`::`域内的东西
>
> **使用案列：**
>
> ```cpp
> #include <iostream>
> 
> int mian()
> {
>     std::cout << "你好" << std::endl;//指定访问std空间域内的endl和cout
>     
>     return 0;
> }
> ```

### 命名空间域展开

> 当我们在开发一个大项目时会发现如果调用一个常用函数在某个域内时，我门需要频繁指定域，这个操作就闲的很繁琐。
>
> 所以，为了解决这个繁琐的操作我们提供了两个解决方案，**如下：**
>
> 1. 全部展开
>
>    > + 优点
>    >
>    >   不用繁琐的一直指定空间域
>    >
>    > + 缺点
>    >
>    >   那么会迎来命名冲突的问题，本身定义这个命名空间域就是防止命名冲突的。
>
>    ```cpp
>    using namespace std;//展开std空间域内的所有东西
>    ```
>
> 2. 部分展开
>
>    > + 优点
>    >
>    >   常用接口可以直接调用不用写繁琐的指定空间域
>    >
>    > + 缺点
>    >
>    >   对于不常用接口来说还是需要繁琐的使用域作用限定符来指定空间域。
>
>    ```cpp
>    using std::cout;//展开std的一个教cout接口
>    ```
>
>    **总结：** 在正式的开发项目全程使用域作用限定符来访问，当然如果想在调用常用接口时不想写繁琐的域作用访问限定符可以是用第二个方案，不建议使用第一种方案如果仅仅是日常写练习代码的话是可以的，正式项目不建议使用第一种方案。



# 🥯🥯🥯缺省参数

### 什么是缺省参数？

> 缺省参数就是有一个默认值，当你不给函数传实参时且该函数有默认参数，那么会使用默认参数如果给实参则使用实参无实参使用默认参数。
>
> 缺省参数必须是从右往左缺省，因为压栈的时候形参是从右往左压栈的，如果是断断续续或者从左往右缺省那么不会构成缺省参数，此时会编译器会报错。

### 全缺省

> 全缺省参数的意思是该函数的所有形参都有一个默认值。
>
> **使用案列：**
>
> ```cpp
> #include <iostream>
> 
> using namespace std;
> 
> int Add(int x = 10, int y = 40)
> {
> 	return x + y;
> }
> 
> int main()
> {
> 	int x = 100;
> 	int y = 30;
> 
> 	cout << Add(x, y) << endl;//传实参不使用缺省参数
> 	cout << Add() << endl;//不传实参使用默认值
> 
> 	return 0;
> }
> ```



### 半缺省参数

> 半缺省参数指的不是有一半形参是有缺省值，而是指部分形参有缺省值，只要不是全缺省那么就是半缺省。
>
> **使用案列：**
>
> ```cpp
> #include <iostream>
> 
> using namespace std;
> 
> int Add(int x, int y = 40)
> {
> 	return x + y;
> }
> 
> int main()
> {
> 	int x = 100;
> 	int y = 30;
> 
> 	cout << Add(x, y) << endl;//传实参不使用缺省参数
> 	cout << Add(x) << endl;//不传实参使用默认值
> 
> 	return 0;
> }
> ```



### 缺省参数的注意事项

> **注意：** 缺省参数的缺省值不能在声明和定义中同时出现，建议缺省值写在声明内因为这样后续更改还是阅读会更好。

# 🍜🍜🍜引用

### 什么是引用？

> 引用相当于给对象取别名，这个别名相当于该对象本身，引用再使用时必须初始化不能像其它对象一样不不初始化再使用，引用一旦引用了一个对象那么该引用的引用对象不能再变更。
>
> 引用可以被其它引用对象引用，也可以多个引用对象引用同一个对象。

### 引用的创建

> **使用方法：**  类型 引用对象名`&` = 引用对象
>
> **使用案列：**
>
> ```cpp
> #include <iostream>
> 
> using namespace std;
> 
> int Add(int x, int y = 40)
> {
> 	return x + y;
> }
> 
> int main()
> {
> 	int a = 50;
> 	int& ra = a;
> 
> 	cout << "ra：" << ra << endl;
> 	cout << "a：" << a << endl;
> 
> 	ra = 100;
> 	cout << "ra：" << ra << endl;
> 	cout << "a：" << a << endl;
> 
> 	return 0;
> }
> ```
>

### 引用的特性

1. 可以被其它引用对象引用
2. 可以多个引用对象引用同一个对象
3. 实列化必须初始化
4. 一旦引用就无法更改引用的对象

### 引用权限放大与缩小问题

### 引用的权限放大

> 当一个对象被`const`修饰过此时再被一个没被`cosnt`修饰过类型的引用来引用该对象则会出现权限的放大问题，因为引用不像指针，如果是指着是可以修改的。
>
> 而引用无法间接修改，一旦被放大权限那么编译器会报错。
>
> **使用案列：**
>
> ```cpp
> #include <iostream>
> 
> using namespace std;
> 
> int main()
> {
> 	const int a = 10;
> 	int& b = a;
> 
> 	return 0;
> }
> ```
>
> ![image-20220218210628684](https://cdn.jsdelivr.net/gh/ls02/Image/img/202210281318134.png)

### 引用的权限缩小

> 　当引用缩小权限引用一个对象时是没问题的，因为你不能写但是对象本身能写，这是不影响的就像住酒店一样，你说你交钱了你不住那也可以，但是你没钱你想住那么这是越界行为是不允许的。
>
> **使用案列：**
>
> ```cpp
> #include <iostream>
> 
> using namespace std;
> 
> int main()
> {
> 	int a = 10;
> 	const int& b = a;
> 
> 	return 0;
> }
> 
> ```



### 引用隐式类型转换过的对象

> 如果引用类型和目标类型不一致且引用对象时发生了隐式类型转换，那么引用的目标则是一个临时空间开辟的一个对象，该对象只能读不能写，如果你想要引用那么需要用`const`修饰。
>
> ```cpp
> #include <iostream>
> 
> using namespace std;
> 
> int main()
> {
> 	int a = 10;
> 	double& b = a;//这里引用的不是a了，因为发生了隐式类型转换所以b引用的是一个临时对象且是只读的，所以该行会报错
> 
> 	return 0;
> }
> ```
>
> ![image-20220219101725412](https://cdn.jsdelivr.net/gh/ls02/Image/img/202210281318163.png)
>
> ![image-20220219101907157](https://cdn.jsdelivr.net/gh/ls02/Image/img/202210281318644.png)

### 引用的优点

> 引用比指针的使用更简单而且一开始必须初始化，这点比指针好很多，指针如果不初始化会形成野指针。
>
> 引用的底层也是指针不过比指针更加简单且强大。
>
> **引用的适用场景：**
>
> 1. 做函数的形参
> 2. 做函数的返回值

#### 值做返回值

> **例子：**
>
> ```cpp
> #include <iostream>
> 
> using namespace std;
> 
> int Add(int a, int b)
> {
> 	int c = a + b;
> 
> 	return c;
> }
> 
> int main()
> {
> 	int& a = Add(40, 30);//不能引用，因为该对象是一个临时对象只能读，如果引用会发生权限的放大所以是不可以引用的
> 
> 	return 0;
> }
> ```
>
> **问题：**a引用的对象是不是c？
>
> **答：** 并不是，因为该栈帧已销毁那么返回值绝对不是c而是一个临时对象但是栈帧已销毁，所以该对象一定不是在Add栈帧内，一定是在main函数栈帧内。
>
> ![image-20220219104217232](https://cdn.jsdelivr.net/gh/ls02/Image/img/202210281318570.png)

#### 引用做返回值

> **例子：**
>
> ```cpp
> #include <iostream>
> 
> using namespace std;
> 
> int& Add(int a, int b)
> {
> 	int c = a + b;
> 
> 	return c;
> }
> 
> int main()
> {
> 	int& a = Add(40, 30);
> 
> 	return 0;
> }
> ```
>
> 引用做返回值，该引用做返回值返回的是c对象，而不是临时空间的对象因为该临时空间类型也是一个引用类型，而外面也用引用类型接收那么便向的引用的是c。
>
> 临时空间的类型是根据返回值类型来决定的，不过该引用c对象引用的是一个已销毁的空间。
>
> ![image-20220219104413743](https://cdn.jsdelivr.net/gh/ls02/Image/img/202210281318488.png)
>
> **注意：** 引用做返回值时，返回的对象不能是被销毁的空间，不然会越界访问，仅仅访问肯定是没问题的，如果进行修改可能会被编译器的检查位检查到从而报错。

### 指针和引用的区别

> **例子：**
>
> ```cpp
> #include <iostream>
> 
> using namespace std;
> 
> int main()
> {
> 	int a = 10;
> 	int& b = a;//从语法角度来理解就是b是a的别名
> 
> 	int* pa = &a;//从语法角度来理解就是创建了一个指针对象指向了a
> 
> 	return 0;
> }
> ```
>
> ![image-20220219154322221](https://cdn.jsdelivr.net/gh/ls02/Image/img/202210281318317.png)
>
> 从语法角度来讲引用是没开辟空间的，而指针是开辟了一个4/8字节大小的空间。
>
> 但是，我们从汇编代码的角度来看都是它两的操作是一摸一样的，都是把a的地址存储到自己的空间里面，由此可以得出结论引用的底层和指针类似，但是引用比指针好理解容易使用。
>
> **主要的几个区别：**
>
> 1. 引用在实列化时必须初始化，指针没有要求
> 2. 引用在初始化时引用一个实体后就不能再引用其它实体对象，而指针可以在任何时候指向一个同类型尸体
> 3. 没有`NULL`引用，但有`NULL`指针
> 4. 在sizeof中的含义不同，引用的大小位引用类型的大小，但指针始终是地址空间所占字节个数（32位平台下占4个字节，64位平台下占8个字节）
> 5. 引用自增时是引用的实体自增1，指针自增1是让指针向后偏移一个类型大小。
> 6. 有多级指针，但是么有多级引用。
> 7. 访问实体方式不同，指着你需要显示解引用，引用编译器自己处理
> 8. 引用比指针使用起来相对安全。



# 🍟🍟🍟函数重载

### 什么是函数重载？

> 函数重载是一个函数名能定义多个函数，这就是函数重载。
>
> **函数重载的构成条件：**
>
> 1. 形参个数不同
> 2. 类型不同

### 函数重载的定义

> **例子：**
>
> ```cpp
> #include <iostream>
> 
> using namespace std;
> 
> int Add(int a, int b)
> {
> 	return a + b;
> }
> 
> double Add(double a, double b)
> {
> 	return a + b;
> }
> 
> int main()
> {
> 	cout << Add(10, 30) << endl;
> 	cout << Add(2.3, 5.3) << endl;
> 
> 	return 0;
> }
> ```
>
> 在们看调用`Add`的时候总觉调的是同一个，其实不然我们调的不是两个不同的函数，而编译器的识别是通过类型识别匹配对应的函数。



### 函数名修饰规则

> C++支持函数名重载的原因是因为C++有也给函数名修饰规则，如果没有该规则是不能进行函数重载的。

**C语言连接时的函数名：**

![image-20220219111306549](https://cdn.jsdelivr.net/gh/ls02/Image/img/202210281318875.png)

**C++链接时的函数名：**

![image-20220219111825239](https://cdn.jsdelivr.net/gh/ls02/Image/img/202210281318691.png)

我们可以从上面的两个图中发现C和CPP的函数名在链接时，它们的函数名时不相同的这也就是为什么C不能支持函数重载，而CPP可以的原因。



### extern "C"的作用

> 当CPP写的中间件想给C使用时我们在C++的函数前面加上`extern "C"`就是可以让C直接调用了，不过使用了`extern "C"`那么该函数会丧失函数重载的能力，因为`extern "C"`是让该函数使用C的函数名修饰规则。



# 🍱🍱🍱内联函数

### 什么是内联函数？

> 在`iniline`修饰的函数叫做内联函数，内联函数的作用是在当前栈帧展开，不建立栈帧因为建立栈帧是有一定的消耗的。

### 内联函数的创建

> 　**使用案列：**
>
> ```cpp
> inline int Add(int a, int b)
> {
> 	return a + b;
> }
> ```

### 内联函数的适用场景

> 只适合小型任务的函数，如果函数过大那么编译器不会让它成为内联函数的。
>
> 1. `inline`是一种空间换时间的做法，省区调用函数栈帧的开销，所以代码很长或者有循环/递归的函数不适合定义成内联函数
> 1. `inline`对编译器来讲只是一种建议，编译器会自动优化，如果定义位`inline`的函数体内有循环/递归等等，会被编译器忽略掉。
> 2. `inline`不建议声明和定义分离，分离会导致链接错误，因为`inline`被展开了，就没有函数地址了，链接就会找不到。

### 默认内联函数

> 当函数是在类里面实现和定义的时候成员函数默认就是被建议成内联函数，除非该函数不符合内联函数的特征，CPU会无视编译器的内联函数

# 🥫🥫🥫类和对象

### 什么是面向对象？

> C++是基于面向对象的，关注的是对象，将一件事情拆分成不同的对象，靠对象之间的交互完成。

### 什么是面向过程？

> C语言是面向过程的，关注的是过程，分析出求解问题的步骤，通过函数调用来逐步结解决。

### 什么是类？

> 类定义的是一个新的类型，类的构成有两部分。
>
> 1. 成员变量（属性）
> 2. 成员函数（行为）

#### 类的创建

> **使用案列：**
>
> ```cpp
> struct Book
> {
>     string name;
>     int price;   
> };
> 
> class Book
> {
>   public:
>     string name;
>     int price;
> };
> ```

##### 面试题：struct和class的区别

> C++里·`struct`可以当成一个结构体单独使用，也可以当成一个类来使用，因为C++为了兼容C所以`struct`就也可以创建类，而`struct`创建的类默认的访问限定符是公有的，而`class`定义的类默认访问限定符是私有的。

##### 内部类

> 内部类顾名思义就是在类里面再定义一个类，这跟C语言的嵌套结构体一样。
>
> 如果想对内部类进行访问必须先指定类再指定内部类。
>
> 如果一个类定义在另一个类的内部，这个内部类就叫做内部类。注意此时这个内部类是一个独立的类，它不属于外部类，更不能通过外部类的对象去调用内部类。外部类对内部类没有任何优越的访问权限。
>
> **注意：** 内部类就是外部类的友元类。注意友元类的定义，内部类可以通过外部类的对象参数来访问外部类中的所有成员。但是外部类不是内部类的友元。

##### 内部类的特性

> 1. 内部类可以定义在外部类的`public`、`protected`、`private`都是可以的。
>
> 2. 注意内部类可以直接访问外部类中的static、枚举成员，不需要外部类的对象/类名。
>
> 3. `sizeof`(外部类)=外部类，和内部类没有任何关系

### 类的访问限定符

![image-20220219162321923](https://cdn.jsdelivr.net/gh/ls02/Image/img/202210281319788.png)

> **访问限定符说明：**
>
> 1. `public`修饰的成员在类外可以直接被访问。
> 2. `protected`和`private`修饰的成员在类外不能直接被访问。
> 3. 访问限定符的作用域从该访问限定符出现到下一个访问限定符出现为止。
> 4. `class`的默认访问限定符位`private`，`struct`为`public`（因为要兼容C）
>
> **注意：** 访问限定符只在编译时有用，当数据映射到内存后，没有任何访问限定符的区别。

### 面向对象的三大特性

#### 封装

> **封装：**将数据和操作数据的方法进行隐藏，不让直接使用而是必须要通过公有的方法来进行访问和操作。
>
> 封装的本质就是对数据的管理，就像去博物馆你想访问里面的物品需要买票进去，而买票是也给公有的方法，而该方法也只能让你在固定安全的访问内访问。

#### 继承



#### 多态



### 类的作用域

> 类域也是一个域，如果需使用类的东西，那么对象会去类域里面进行查找。

#### 类的大小计算

> 再算一个类所占空间时是不计算成员函数的，只计算成员对象而成员对象又需要独立开辟空间所以在计算类的大小时计算的是类的成员对象。
>
> ```cpp
> #include <iostream>
> 
> using namespace std;
> 
> class A
> {
> private:
> 	char ch;
> 	int a;
> };
> 
> //空类
> class B
> {
> 
> };
> 
> int main()
> {
> 	cout << sizeof(A) << endl;
> 	cout << sizeof(B) << endl;
> 
> 	return 0;
> }
> ```
>
> ![image-20220219170456013](https://cdn.jsdelivr.net/gh/ls02/Image/img/202210302251276.png)
>
> 我们可以看到在计算空类时并不是没有占空间，而是用了一个字节来占空间。
>
> 如果，不用一个字节来占空间，那么这个类将找不到，所以必须得要一个字节来占位。

### this指针

> `this`指针是一种隐含的参数，在C++里面是作为一个关键字，它的主要作用是默认指向该对象的地址。
>
> **使用案例：**
>
> ```cpp
> #include <iostream>
> 
> using namespace std;
> 
> class Data
> {
> private:
> 	int year;
> 	int month;
> 	int day;
> 
> public:
> 	Data(int year, int month, int day)//这里看起来只有三个参数实际上有四个，还有一个是this指针不过被隐含了
> 	{
> 		this->year = year;
> 		this->month = month;
> 		this->day = day;
> 	}
> };
> 
> int main()
> {
> 	Data d1(2020, 2, 4);
> 
> 	return 0;
> }
> ```
>
> ![image-20220220085346120](https://cdn.jsdelivr.net/gh/ls02/Image/img/202210312141868.png)

### 六个默认成员函数

![image-20220220085850464](https://cdn.jsdelivr.net/gh/ls02/Image/img/202210292118147.png)

#### 构造函数

##### 默认构造函数

> 默认构造函数指的是无需给值就能创建对象的就是默认构造函数，如果需要传值才能创建对象的都是构造函数。
>
> **使用案列：**
>
> ```cpp
> int main()
> {
>     Data d1;//这里调用的是默认构造函数
>     Data d2(2022, 2, 3);//这里调用的是构造函数
>     
>     return 0;
> }
> ```



##### 默认构造函数的特性

> 只要能不传参就能构造对象的就是默认构造函数，全缺省的和编译器自己生成的，都是叫默认构造函数。
>
> 默认构造函数有个特点，就是不会对内置类型进行任何操作，会调用自定义类型的构造函数。
> **三种：**
>
> 1. 编译器自动生成的
> 2. 写的无参的
> 3. 全缺省的
>
> **总结：** 不用参数就能调用的构造函数就是默认构造函数。

#### 构造函数的特性

> 构造函数是特殊的成员函数，需要注意的是，构造函数的名称虽然叫构造函数但是任务不是创建对象和开辟空间，而是用于初始化对象。
>
> 构造函数会自动调用，当对象实列化时就会自动调用构造函数。
> **主要特征：**
>
> 1. 函数名域类名相同
> 2. 无返回值
> 3. 对象实例化时编译器自动调用对应的构造函数。
> 4. 构造函数可以重载

#### 初始化列表

> 初始化列表：以一个冒号开始，接着是以一个逗号分隔数据成员列表。
>
> 一下成员只能在初始化列表内完成初始化，构造函数无法完成。
>
> 1. `const`修饰的成员变量
> 2. 引用成员变量
> 3. 自定义类型成员（该类没有默认构造函数）
>
> **注意：** 每个成员只能初始化一次，如果在初始化列表内初始化过，那么就不能在构造函数内赋值初始化。
>
> **使用案列：**
>
> ```cpp
> #include <iostream>
> 
> using namespace std;
> 
> class A
> {
> public:
> 	A(int a)
> 	{
> 		_a = a;
> 	}
> 
> 	int GetA(void)
> 	{
> 		return _a;
> 	}
> private:
> 	int _a;
> };
> 
> 
> class Date
> {
> public:
> 	Date(int day, int& ra)
> 		:_day(day)
> 		,_A(20)
> 		,_ra(ra)
> 	{
> 
> 	}
> 
> 	void Print(void)
> 	{
> 		printf("_day:%d\n_A:%d\n_ra:%d\n", _day, _A.GetA(), _ra);
> 	}
> private:
> 	const int _day;
> 	A _A;
> 	int& _ra;
> };
> 
> 
> int main()
> {
> 	int b = 50;
> 	Date d1(1000, b);
> 
> 	d1.Print();
> 
> 	return 0;
> }
> ```

#### 初始化列表初始化顺序

> 初始化列表的初始化顺序是根据，成员变量的声明顺序为主，跟初始化列表的顺序无关。
>
> **例子：**
>
> ```cpp
> class A {
> public:
>     A(int a)//初始化列表的初始化顺序和此处无关
>         :_a1(a)
>         ,_a2(_a1)
>         {}
>  
>  void Print() {
>      cout<<_a1<<" "<<_a2<<endl;
>  }
> private://此处的变量是声明，初始化顺序和此处有关
>     int _a2;
>     int _a1;
> }
> 
> int main() {
>     A aa(1);
>     aa.Print();
> }
> ```

### 单参数的构造函数

> 当一个类的成员变量只有一个时，且是内置类型那么就可以使用单参数的构造函数。
>
> **例子：**
>
> ```cpp
> #include <iostream>
> using namespace std;
> 
> class Date
> {
> public:
>     Date(int day)
>     {
>         _day = day;
>     }
>     
>     
> private:
>     int _day;
> }
> 
> int main()
> {
>     Date d1 = 3;//这里的行为其实是隐式类型转换，编译器会先构造一个临时对象然后把3给这个临时对象，再调用拷贝构造把这个临时对象的值拷贝给d1，这是旧版的编译器
>     //新版的编译器已经优化了，它会直接拿这个3调用一个构造。所以实际上只调用了一次构造，和上面的调用了两次构造一次默认构造和一次拷贝构造
>     
>     return 0;
> }
> ```

### explicit

> 该关键字是C++引入的关键字，主要用途是用来警用单参数的构造函数。
>
> 该关键字加再构造函数前面，这样就能让单参数的构造函数无法发生隐式类型转换从而导致单参数的构造函数失效。
>
> ```c
> #include <iostream>
> using namespace std;
> 
> class Date
> {
> public:
>     explicit Date(int day)//禁用单参数的构造函数
>     {
>         _day = day;
>     }
>     
>     
> private:
>     int _day;
> }
> 
> int main()
> {
>     Date d1 = 3;//这里的行为其实是隐式类型转换，编译器会先构造一个临时对象然后把3给这个临时对象，再调用拷贝构造把这个临时对象的值拷贝给d1，这是旧版的编译器
>     //新版的编译器已经优化了，它会直接拿这个3调用一个构造。所以实际上只调用了一次构造，和上面的调用了两次构造一次默认构造和一次拷贝构造
>     
>     return 0;
> }
> ```

### 匿名对象

> 匿名对象的生命周期只在定义的该行，过了改行就会立刻调用析构函数进行资源的清理。
>
> **使用案列：**
>
> ```cpp
> #include <iostream>
> 
> using namespace std;
> 
> class Date
> {
> public:
>     void Print(void)
>     {
>         cout << "你好" << endl;
>     }
> }
> 
> int main()
> {
>     Date().Print();//构造一个匿名对象并调用改匿名对象的Print()成员函数
>     Date();//构造一个匿名对象
>     
>     return 0;
> }
> ```



#### 析构函数

> 析构函数主要是完成资源的清理。

#### 析构函数的特点

> ​	析构函数是一个特殊的默认成员函数，它是用来完成资源的释放。
> ​	**其特征：**
>
> 1. 类名前面加"~"
> 2. 无参数无返回值
> 3. 一个类只有一个析构函数，如果没写编译器会自动生成一个默认析构函数
> 4. 对象的生命周期结束时，编译器会自动调用该对象的析构函数进行资源的释放。
>
> **使用案列：**
>
> ```cpp
> class Data
> {
>     ~Data()//析构函数
>     {
>         
>     }
> }
> ```

#### 析构顺序

> 由于在实列化对象时大部分都是在栈上开辟空间，所以先构造的后析构，后构造的先析构，符合栈的先进后出。

#### 默认析构函数

> 默认析构函数和默认构造函数一样，不会对内置类型进行任何处理，会对自定义类型进行调用它的析构。

#### 析构和构造函数的总结

> **总结：** 构造函数和析构函数都对内置类型不进行任何处理，对自定义类型会调用自定义类型的析构和构造。

#### 运算符重载

##### 什么是运算符重载？

> C++为了增强代码的可读性引入了运算重载，运算符重载是一种特殊的具有函数名的函数，也具有返回值类型，函数名字以及参数列表。
>
> **注意事项：**
>
> + 不饿能通过连接其它符号来创建新的操作符：比如：operator@
> + 重载操作符必须有一个类类型或者枚举类型的操作数。
> + 用于内置类型的操作符，其含义不能改变，例如：内置类型+，不饿能改变其含义。
> + 作为类成员的重载函数时，其形参看起来比操作数数目少1成员函数的,操作符有一个默认的形参this，限定为第一个形参
> + ``.*``、`::`、`sizeof`、`?:`、`.`注意这五个运算符不能重载。
>
> **使用方式：** 返回值 `operator`重载符号(`void`);
>
> **使用案列：**
>
> ```cpp
> class Add
> {
> public:
>     int operator+(const Add& a)
>     {
>         this->a += a;
>         
>  		return this->a;
>     }
> private:
>     int a;
> }
> ```



####  拷贝构造

##### 什么是拷贝构造？

> 拷贝构造是一种特殊的构造函数，不过它主要是用来给相同类对象初始化的。
>
> **拷贝构造的特征：**
>
> 1. 拷贝构造函数时构造函数的一个重载形式
> 2. 拷贝构造函数的参数只有一个且必须使用引用传参，使用传值方式会发生无穷递归。
>
> **使用案列：**
>
> ```cpp
> class Date
> {
> public:
> 	Date(const Date& d1)//拷贝构造
>     {
>         _year = d1._year;
>         _month = d1._month;
>         _day = d1._day;
>     }
> private:
>     int _year;
>     int _month;
>     int _day;
> }
> ```



#### 默认拷贝构造

> 默认拷贝构造就是我们不写编译器自动生成的就是默认拷贝构造。
>
> 默认拷贝构造会对内置类型进行值拷贝（浅拷贝），对自定义类型会调用它的拷贝构造。

##### 浅拷贝

> 浅拷贝就像C语言里的函数形参传递一样，形参的改变不会影响到实参。
>
> 浅拷贝不会独立开辟空间，而是把传递过来的值直接拷贝给对象。

##### 深拷贝

> 深拷贝就像C语言里的址传递，形参的改变会影响到实参。
>
> 深拷贝会开辟独立的空间且初始化为形参的值，再拷贝给对象。

#### 赋值重载

##### 什么是赋值重载

> 赋值重载也是六个默认特殊成员函数的一种。
>
> **主要特征如下：**
>
> 1. 参数类型
> 2. 返回值
> 3. 检测是否自己给自己赋值
> 4. 返回`*this`
> 5. 一个类如果没有显示定义赋值运算符重载，编译器也会自动生成一个，完成对象按字节序的值拷贝。
>
> **使用案列：**
>
> ```cpp
> class Date
> {
> public:
> 	Date(const Date& d1)//拷贝构造
>     {
>         _year = d1._year;
>         _month = d1._month;
>         _day = d1._day;
>     }
>     
>     Date& operator=(const Date& d1)//赋值重载
>     {
>         _year = d1._year;
>         _month = d1._month;
>         _day = d1._day;
>     }
> private:
>     int _year;
>     int _month;
>     int _day;
> }
> ```



#### 默认赋值重载

> 赋值默认重载我们不写，编译器生成的赋值重载，它会对自定义类型进行值拷贝，而对自定义类型会调用它对应的赋值重载。

#### 拷贝构造和赋值重载总结

> **总结：** 拷贝构造和赋值重载，会对内置类型进行值拷贝，对自定义类型进行调用它们对应的拷贝构造和赋值重载。



### const修饰成员函数

> 有时候我们不想让`this`指针的内容被改变时，我们就需要给`this`指针加上`const`来修饰但是问题时，`this`指针是隐含的无法直接修饰。
>
> 所以，C++支持另一种方式来修饰只需在该函数的括号外加上`const`就是对`this`指针的修饰了。
>
> **使用案列：**
>
> ```cpp
> 	bool operator!=(const Date& d)const//这里的const修饰的是this指针
> 	{
> 		return !(*this == d);
> 	}
> ```

### 取地址重载

> 取地址重载几乎没用，因为99%的情况下默认生成的取地址重载就够用了。
>
> **例子：**
>
> ```cpp
> class Date
> {
> private:
> 	int _year;
> 	int _month;
> 	int _day;
> public:
>     Date* operator&()//取地址重载
>     {
>         return this;
>     }
> }
> ```

### const修饰的取地址重载

> 有时候我们对只读对象进行取地址时就必须要用`const`修饰的取地址重载才能进行调用。
>
> **例子：**
>
> ```cpp
> class Date
> {
> private:
> 	int _year;
> 	int _month;
> 	int _day;
> public:
>     Date* operator&()//取地址重载
>     {
>         return this;
>     }
>     
>     Date* operator&()const//const修饰的取地址重载
>     {
>         return this;
>     }
> }
> ```



#### const取地址重载和取地址重载总结

> 这两个特殊成员函数没有实现的价值，我们只需要使用编译器生成的默认特殊成员函数就可以了，因为这两个也是六个默认成员函数中的两种，所以编译器会自动生成。





## 友元

> 友元分为： **友元函数** 和 **友元类**
>
> 友元提供了一种突破封装的方式，有时提供了便利，但是友元会增加耦合度，破化了封装所以友元尽量少用。

### 友元函数

> 友元函数就如同它的名字一样，一个类具有封装性我们是无法直接在类外访问的，而有些特殊场景下我们需要访问的话，我们就定义成友元函数这样一个函数是另一个的类的友元就能直接访问该类中的私有成员了。
>
> 当然使用了友元就会破坏封装除非特殊情况，一般是不建议使用友元函数的。
>
> **使用方法：** `friend`  返回值类型 函数名(参数);
>
> **使用案列：**
>
> ```cpp
> class Date
> {
> 	friend std::ostream& operator<<(std::ostream& out, const Date& d);//该函数时这个类的友元
> private:
> 	int _year;
> 	int _month;
> 	int _day;
> public:
>     Date* operator&()//取地址重载
>     {
>         return this;
>     }
>     
>     Date* operator&()const//const修饰的取地址重载
>     {
>         return this;
>     }
> }
> ```
>

#### 友元函数的特点

> **友元函数**可以**直接访问**类的**私有**成员，它是**定义在类外部**的**普通函数**，不属于任何类，但需要在类的内部声明，声明时需要加**friend**关键字。
>
> **特点：**
>
> 1. 友元函数可以访问类的私有成员，但不是类的成员函数
> 2. 友元函数不能用`const`修饰
> 3. 友元函数可以类定义的任何地方声明，不受类的访问限定符限制。
> 4. 一个函数可以是多个类的友元函数。
> 5. 友元函数的调用与普通函数的调用和原理相同。

### 友元类

> 友元类的所有成员函数都可以是另一个类的友元函数，都可以访问另一个类中的非公有成员。
>
> + 友元是单向的关系，不具有交换性（我是你的朋友我能访问你，但是你们不能访问的东西）
> + 友元关系不能传递
>
> **使用案列：**
>
> ```cpp
> #include <iostream>
> 
> using namespace std;
> 
> class B;//前置声明
> class A
> {
> 	friend class B;//B是A的友元B能访问A的所有成员
> public:
> 	A(int a = 5)
> 	{
> 		_a = a;
> 	}
> 
> 	void PrintA(void)
> 	{
> 		cout << "A" << endl;
> 	}
> 
> private:
> 	int _a;
> };
> 
> class B
> {
> public:
> 	B(int b = 10)
> 	{
> 		_b = b;
> 	}
> 
> 	void PrintB(void)
> 	{
> 		
> 		cout << "B:" << _b << "\t_A:" << _A._a << endl;
> 		_A.PrintA();
> 	}
> 
> private:
> 	int _b;
> 	A _A;
> };
> 
> int main()
> {
> 	A a;
> 	B b;
> 
> 	b.PrintB();
> 
> 	return 0;
> }
> ```



### static成员

#### 什么是static成员？

> 声明为`static`类型的类成员称为类的静态成员，用`static`修饰的成员对象叫静态成员对象，用`static`修饰的成员函数称为静态成员函数。
>
> 静态成员函数，只能在类外面初始化，不能在类里初始化因为静态成员没有`this`指针无法通过初始化列表和构造函数初始化。
>
> 静态成员变量不存放在栈里，存放在静态区且属于整个类，不属于某个对象所有对象看到的静态成员你都是同一个。
>
> **使用案列：**
>
> ```cpp
> #include <iostream>
> 
> using namespace std;
> 
> class A
> {
> public:
> 	static int _a;
> };
> 
> int A::_a = 20;//对静态成员初始化，
> 
> int main()
> {
> 	A a1;
> 	A a2;
> 
> 	cout << a1._a << endl;
> 	cout << a2._a << endl;
> 
> 	a1._a++;
> 
> 	cout << a1._a << endl;
> 	cout << a2._a << endl;
> 
> 	return 0;
> }
> ```

### 静态成员特征

> 1. **静态成员** 为所有**类对象所共享** ，不属于某个具体的实例
>
> 2. **静态成员变量** 必须在**类外定义** ，定义时不添加static关键字
>
> 3. 类静态成员即可用类名`::`静态成员或者对象.静态成员来访问
>
> 4. 静态成员函数**没有** 隐藏的**this** **指针** ，不能访问任何非静态成员
>
> 5. 静态成员和类的普通成员一样，也有`public`、`protected`、`private`3种访问级别，也可以具有返回值。
>
> **问题：** 
>
> 静态成员函数可以调用非静态成员函数吗？
>
> **答：** 不可以，因为静态成员函数没有`this`指针，那么调用非静态成员需要`this`指针没有`this`指针编译器调用不了。
>
>  非静态成员函数可以调用类的静态成员函数吗？
>
> **答：** 可以，因为不需要`this`指针调用它。

### 声明缺省值

> C++11支持非静态的成员对象在声明时给缺省值。
>
> **注意：** 此处是缺省值，不是对象实例化和初始化，缺省值只有内置类型能使用，如果又构造函数就会用构造函数内的参数，如果没有编译器生成的默认构造函数就会使用缺省值，没有缺省值的话就是随机值。
>
> **使用案列：**
>
> ```cpp
> #include <iostream>
> 
> using namespace std;
> 
> class A
> {
> public:
> 	void Print(void)
> 	{
> 		cout << _a << endl << _b << endl;
> 	}
> private:
> 	int _a = 20;//这里是声明，给声明缺省值并不是定义初始化
> 	int _b = 30;
> };
> 
> int main()
> {
> 	A a1;
> 
> 	a1.Print();
> 
> 	return 0;
> }
> 
> ```

# 🍭🍭🍭内存管理

>  C语言内存管理方式在C++中可以继续使用，但有些地方就无能为力而且使用起来比较麻烦，因此C++又提出了自己的内存管理方式：通过` new`和`delete`操作符进行动态内存管理。

## new关键字

> C++的关键字`new`用于动态申请，如果是申请自定义类型那么会自动调用该自定义类型的构造函数。
>
> **使用方式：** new 类型名;
>
> **使用案列：**
>
> ```cpp
> #include <iostream>
> 
> using namespace std;
> 
> int main()
> {
> 	int* p1 = new int;//动态申请一个整形
> 	int* p2 = new int(30);//动态申请一个整型并初始化成30
> 	int* p3 = new int[20];//动态申请20个整型
> 	int* p4 = new int[5]{ 1, 2, 3, 4, 5 };//动态申请5个整型并初始化成1 2 3 4 5；
> 
> 	return 0;
> }
> ```



## delete关键字

> `delete`作用：用于释放动态资源
>
> **使用方式：** delete 变量名
>
> **使用案列：**
>
> ```cpp
> #include <iostream>
> 
> using namespace std;
> 
> int main()
> {
> 	int* p1 = new int;//动态申请一个整形
> 	int* p2 = new int(30);//动态申请整型并初始化成30
> 	int* p3 = new int[20];//动态申请多个个整型
> 	int* p4 = new int[5]{ 1, 2, 3, 4, 5 };//动态申请5个整型并初始化成1 2 3 4 5；
> 
> 	delete p1;//释放一个动态内存
> 	delete p2;
> 	delete[] p3;//释放多个节点必须使用[]否则会出现不可预知的问题
> 	delete[] p4;
> 
> 	return 0;
> }
> ```
>

## operator new与operator delete函数

>`new`和`delete`是C++提供给用户自定义申请内存和释放内粗的关键字，而这两个关键字底层会调用全局的`operator new`和`operator delete`函数来申请和释放内存。
>
>![image-20220223114130635](https://cdn.jsdelivr.net/gh/ls02/Image/img/202210281317114.png)
>
>而`operator new`和`operator delete`的底层又是调用`malloc()`和`free()`。
>
>```cpp
>_CRT_SECURITYCRITICAL_ATTRIBUTE
>void* __CRTDECL operator new(size_t const size)
>{
>    for (;;)
>    {
>        if (void* const block = malloc(size))
>        {
>            return block;
>        }
>
>        if (_callnewh(size) == 0)
>        {
>            if (size == SIZE_MAX)
>            {
>                __scrt_throw_std_bad_array_new_length();
>            }
>            else
>            {
>                __scrt_throw_std_bad_alloc();
>            }
>        }
>
>        // The new handler was successful; try to allocate again...
>    }
>}
>```

**总结：** 不管是`new`还是`operator new`申请内存都是要调用`malloc`来向系统申请，而它两的使用方法也完全一样，唯一的区别就是`operator new`会有抛异常处理，而`malloc`则没有。



## operator new和operator delete重载

> 该重载是用于使用自己或它人写的内存池才重载，虽然内存池的内存也是通过`malloc`向系统申请的，但是它是一次性申请很多内存如果需要内存直接从内存池取，而如果使用`malloc`来申请会恨频繁从而导致效率的下降，如果有一个内存池那么将会提高向系统申请内存的效率。
>
>  ![image-20220223120318921](https://cdn.jsdelivr.net/gh/ls02/Image/img/202210281317003.png)

## 定位new

> 定位`new`一般也是用于搭配内存池使用，而定位`new`在使用时必须是指针变量。
>
> **使用方法：** `new`(指针变量) 类型 或 `new`（指针变量） 类型(指定初始化值)
>
> **使用案列：**
>
> ```cpp
> #include <iostream>
> 
> class A
> {
> public:
> 	A(int a = 0)
> 		:_a(a)
> 	{}
> 
> private:
> 	int _a;
> };
> 
> int main()
> {
> 	A* p1 = (A*)malloc(sizeof(A));
> 	A* p2 = (A*)malloc(sizeof(A));
> 
> 	//定位new
> 	new(p1) A;//调用A的构造函数给p1的指向初始化
> 	new(p2) A(20);//调用A的构造函数给p1的指向初始化成指定值
> 
> 	return 0;
> }
> ```



## new和delete实现原理

### 内置类型

> 如果申请的是内置类型的空间，`new`和`malloc`，`delete`和`free`基本类似，不同的地方是：`new`/`delete`申请和释放的是单个元素的空间，`new`[]和`delete`[]申请的是连续空间，而且`new`在申请空间失败时会抛异常，`malloc`会返回`NULL`。

### 自定义类型

> + `new`的原理
>   1. 调用`operator new`函数申请空间
>   2.  在申请的空间上执行构造函数，完成对象的构造
> + `delete`的原理
>   1. 在空间上执行析构函数，完成对象中资源的清理工作
>   2. 调用operator delete函数释放对象的空间
> + `new T[]`的原理
>   1. 调用operator new[]函数，在operator new[]中实际调用operator new函数完成N个对象空间的申请
>   2. 在申请的空间上执行N次构造函数
> + `delete[]`的原理
>   1. 在释放的对象空间上执行N次析构函数，完成N个对象中资源的清理
>   2. 调用operator delete[]释放空间，实际在operator delete[]中调用operator delete来释放空间

## C++的动态申请释放和C语言的有何区别

> `malloc`/`free`和`new`/`delete`的共同点是：都是从堆上申请空间，并且需要用户手动释放。
>
> **不同的地方是：**
>
> 1. `malloc`和`free`是函数，`new`和`delete`是操作符
>
> 2. `malloc`申请的空间不会初始化，`new`可以初始化
>
> 3. `malloc`申请空间时，需要手动计算空间大小并传递，`new`只需在其后跟上空间的类型即可
>
> 4. `malloc`的返回值为`void*`, 在使用时必须强转，`new`不需要，因为`new`后跟的是空间的类型
>
> 5. `malloc`申请空间失败时，返回的是`NULL`，因此使用时必须判空，`new`不需要，但是`new`需要捕获异常
>
> 6. 申请自定义类型对象时，`malloc`/`free`只会开辟空间，不会调用构造函数与析构函数，而`new`在申请空间后会调用构造函数完成对象的初始化，`delete`在释放空间前会调用析构函数完成空间中资源的清理

## 什么是内存泄漏？

>**什么是内存泄漏：** 内存泄漏指因为疏忽或错误造成程序未能释放已经不再使用的内存的情况。
>
>内存泄漏并不是指内存在物理上的消失，而是应用程序分配某段内存后，因为设计错误，失去了对该段内存的控制，因而造成了内存的浪费。

### 内存泄漏的危害

> **内存泄漏的危害：** 长期运行的程序出现内存泄漏，影响很大，如操作系统、后台服务等等，出现内存泄漏会导致响应越来越慢，最终卡死。

### 内存泄漏的分类

> **C/C++程序中一般我们关心两种方面的内存泄漏：**
>
> + **堆内存泄漏**(`Heap leak`)
>
>   堆内存指的是程序执行中依据须要分配通过`malloc `/ `calloc `/ `realloc `/ new等从堆中分配的一块内存，用完后必须通过调用相应的 `free`或者`delete `删掉。
>
>   假设程序的设计错误导致这部分内存没有被释放，那么以后这部分空间将无法再被使用，就会产生`Heap Leak`。
>
> + **系统资源泄漏**
>
>   指程序使用系统分配的资源，比方套接字、文件描述符、管道等没有使用对应的函数释放掉，导致系统资源的浪费，严重可导致系统效能减少，系统执行不稳定。

### 如何避免内存泄漏？

> 1. 工程前期良好的设计规范，养成良好的编码规范，申请的内存空间记着匹配的去释放。ps：这个理想状态。
>
>    但是如果碰上异常时，就算注意释放了，还是可能会出问题。需要下一条智能指针来管理才有保证。
>
> 2. 采用RAII思想或者智能指针来管理资源。
>
> 3. 有些公司内部规范使用内部实现的私有内存管理库。这套库自带内存泄漏检测的功能选项。
>
> 4. 出问题了使用内存泄漏工具检测。ps：不过很多工具都不够靠谱，或者收费昂贵。
>
> **总结：** 内存泄漏非常常见，**解决方案分为两种：**
>
> 1. 事前预防型。如智能指针等。
>
> 2. 事后查错型。如泄漏检测工具。



# 模板

## 泛型编程

> 泛型编程是指一个函数能适应各种不同类型的参数，如果C++想实现泛型编程的话可以使用函数重载来完成，**但是有几点不好的地方，如下：**
>
> 1. 重载的函数仅仅只是类型不同，代码的复用率比较低，只要有新类型出现时，就需要增加对应的函数
> 2. 代码的可维护性比较低，一个出错可能所有的重载均出错
>
> C++为了完美的实现泛型编程于是推出了一个新概念：**模板**

### 函数模板

#### 什么是函数模板？

> 函数模板代表了一个函数家族，该函数模板与类型无关，在使用时被实列化会根据实参的类型来产生特定类型版本。

#### 函数模板格式

> `template <class A, ..., class B>` 或 `template <typename A, ……, typename B>`
>
> **使用案列：**
>
> ```cpp
> #include <iostream>
> 
> template<class T>
> void Swap(T& left, T& right)
> {
> 	T temp = left;
> 	left = right;
> 	right = temp;
> }
> ```

#### 函数模板原理

>  在编译阶段时，对于模板函数的使用，编译器需要根据传入的实参类型来推演而生成对应类型的函数以供调用。
>
> ![image-20220223125259770](https://cdn.jsdelivr.net/gh/ls02/Image/img/202210281317046.png)

#### 函数模板实列化

> 用不同类型的参数使用函数模板时，称为函数模板的实列化，**模板参数实列化分为两种：**
>
> 1. 隐式实列化
>
>    让编译器根据实参的类型来推演实际类型
>
>    ```cpp
>    #include <iostream>
>    
>    template<class T>
>    void Swap(T& left, T& right)
>    {
>    	T temp = left;
>    	left = right;
>    	right = temp;
>    }
>    
>    int main()
>    {
>    	int a = 10;
>    	int b = 20;
>    
>    	Swap(a, b);//隐式实列化
>    
>    	return 0;
>    }
>    ```
>
> 2. 显示实列化
>
>    ```cpp
>    #include <iostream>
>                                           
>    template<class T>
>    void Swap(T& left, T& right)
>    {
>    	T temp = left;
>    	left = right;
>    	right = temp;
>    }
>                                           
>    int main()
>    {
>    	int a = 10;
>    	int b = 20;
>                                           
>    	Swap<int>(a, b);//显示实列化
>                                           
>    	return 0;
>    }
>    ```

## 类模板

### 类模板定义

> ```cpp
> #include <iostream>
> 
> template <class T>
> class A
> {
> 	T _a;
> 	T _b;
> };
> ```

### 类模板的实列化

> 类模板实列化与函数模板实列化不同，类模板实列化需要在类模板名字后跟`<>`，然后将实列化的类型放在`<>`中即可，类模板名字不是真正的类，而实列化的结果才是真正的类。
>
> **使用案列：**
>
> ```cpp
> #include <iostream>
> 
> template <class T>
> class A
> {
> 	T _a;
> 	T _b;
> };
> 
> int main()
> {
> 	A<int> a;
> 	A<double> b;
> }
> ```



### 模板参数

模板参数有两种分别是：类型参数和非类型参数，我们平常开发用到最多的就是类型参数很少用非类型参数，但是有些场景下却很需要非类型参数。

**类型参数的定义：**

```cpp
template<class T>
class A
{
    T data;
}
```

**非类型参数的定义：**

```cpp
template<size_t N>
class A
{
    int arr[N];
}
```

**注意：非类型模板参数只能使用整型，其它类型无法使用**

### 模板特化

有时候我们在使用模板时有些场景下实列化的逻辑是错误的，这个时候我我们需要针对这种场景进行处理，但是我们只有这一个场景需要处理又不想全部重整这时我们就可以使用函数特化来重构逻辑。

#### 函数特化

函数特化只需要在写一个相同的函数然后模板选无参函数名后面显示实例化类型即可。

```cpp
template<class T>
bool Equal(const T left, const T right)
{
	std::cout << "未特化" << std::endl;

	return left == right;
}

//特化
template<>
bool Equal<const char*>(const char* left, const char* right)
{
	std::cout << "特化" << std::endl;

	return strcmp(left, right) == 0;
}


int main(void)
{
	char str1[] = "hello";
	char str2[] = "hello";

	const char* p1 = "hello";
	const char* p2 = "hello";

	std::cout << Equal(1, 3) << std::endl;
	std::cout << Equal(1.1, 1.1) << std::endl;
	std::cout << Equal("nihao", "nihao") << std::endl;
	std::cout << Equal(str1, str2) << std::endl;
	std::cout << Equal(p1, p2) << std::endl;

	return 0;
}
```



#### 类特化

类特化显示指定特化类型需要在类名后面用`<>`来显示特化。

```cpp
#include <iostream>

template<class T, class P>
class A
{

public:
	A(void)
	{
		std::cout << "未特化" << std::endl;
	}

	T a;
	P b;
};

//全特化
template<>
class A<int, int>
{
public:
	A(void)
	{
		std::cout << "全特化" << std::endl;
	}

	int a;
	int b;
};

//偏特化
template<class T>
class A<T, int>
{
public:
	A(void)
	{
		std::cout << "偏特化" << std::endl;
	}

	T a;
	int b;
};


int main(void)
{
	A<int, int> a;
	A<double, double> b;
	A<double, int> c;

	return 0;
}
```

### 全特化&偏特化

+ 全特化

  全特化是指模板参数都是指定显示特化

+ 偏特化

  偏特化是指一个或多个模板参数是显示特化。

# 继承

## 什么是继承？

继承机制是面向对象程序审计使代码可以复用的一种重要手段，它允许程序员在保持原有类的基础上进行扩展，增加功能这样产生的新类我们称之为派生类（子类）。

继承呈现了面向对象程序设计的层次结构，体现了由简单到复杂的认知过程，以前我们接触的复用都是函数复用，继承是类设计层次的复用。

## 继承的定义

**定义格式：**

```cpp
#include <stdio.h>

//基类(父类）
class A
{
private:
	int _a = 1;
};

//B继承A，继承方式是共有继承
//B是派生类（子类）
class B : public A
{
private:
	int _b = 2;
};

void Test1(void)
{
	A a;
	B b;
}

int main(void)
{
	Test1();

	return 0;
}
```

继承有多种方式分别是：公有继承、保护继承和私有继承。

每一种继承方式都不同主要是针对成员，而继承方式的优先级是：公有继承>保护继承>私有继承。

如果是私有继承或私有成员的话，那么对于子类来讲是看不到父类的私有成员或整个成员，主要是取决于继承方式还有该成员的属性往小的取。

**总结：**

1. 基类`private`成员在派生类中无论以什么形式继承都是不可见的，这里的不可见是指基类的私有成员还是被继承到了派生类对象中，但是语法上限制派生类对象不管在类里面还是在类外面都不能取访问它。
2. 基类`private`成员在派生类中式不能被访问，如果基类成员不想再类外面被直接访问，但需要再派生类中能被访问就定义成`protected`，可以看出保护成员限定符式因继承才出现的。
3. 使用关键字`class`时默认的继承方式是`private`，使用`struct`时默认的继承方式时`public`，不过最好显示的写出继承方式。
4. 在实际运用中一般使用都是`public`继承，几乎很少使用`protetced/private`继承下来的成员都只能在派生类的类里面使用，实际中的扩展维护性不强。

## 赋值兼容

+ 派生类对象可以赋值给基类的对象、基类的指针和基类的引用，这里有个形象的说法叫做切片或叫做切割，寓意吧派生类中的父类那部分切来赋值过去。

+ 基类对象不能赋值给派生类对象。

+ 基类的指针可以通过强制类型转换赋值给派生类的指针，但是必须是基类的指针是指向派生类对下给你时才是安全的，这里基类如果是多态类型，可以使用`RTTI(Run-Time Type Information)`的

  [[dynamic_cast](https://baike.baidu.com/item/dynamic_cast)]:来进行识别后进行安全转换。

  

  ```cpp
  #include <iostream>
  
  class A
  {
  public:
  	A(int a = 10)
  	{
  		_a = a;
  	}
  private:
  	int _a = 1;
  };
  
  class B : public A
  {
  public:
  	B(int b = 20)
  		:A::A(100)
  	{
  		_b = b;
  	}
  private:
  	int _b = 2;
  };
  
  void Test1(void)
  {
  	A a;
  	B b;
  	a = b;
  	A* pa = &b;
  	A& ra = b;
  }
  
  int main(void)
  {
  	Test1();
  
  
  	return 0;
  }
  ```

  ## 继承的作用域

  1. 在继承体系中基类和派生类都有独立的作用域
  2. 子类和父类中有同名成员，子类成员将屏蔽父类对同名成员的直接访问，这种情况叫做隐藏，也叫重定义。（在子类成员函数中，可以使用 `基类::基类成员` 显示访问）
  3. 需要注意的是如果是成员函数的隐藏，只需要函数名相同就构成隐藏。
  4. 注意在实际中在继承体系里面最好不要定义同名的成员。

  ### 派生类的默认成员函数

  ​	六个默认成员函数，“默认”的意思就是指我们不写，编译器会为我们自动生成一个，那么在派生类中，这几个成员函数是如何生成的呢？

  1. 派生类的构造函数必须调用基类的构造函数初始化基类的那一部分成员函数，如果基类没有默认的构造函数，则必须在派生类构造函数的初始化列表阶段显示调用。
  2. 派生类的拷贝构造函数必须调用基类的拷贝构造完成基类的拷贝初始化。
  3. 派生类的`operator`=必须要调用基类的`opeartor`=完成基类的复制。
  4. 派生类的析构函数会在被调用完成后自动调用基类的析构函数清理基类成员，因为这样才能保证派生类对象先清理派生类成员再清理基类成员的顺序。
  5. 派生类对象初始化调用基类构造再派生类的构造。

  ## 继承与友元

  友元关系不能被继承，也就是说基类友元不能访问子类私有和保护成员。

  

  

  ## 继承与静态成员

  ​	基类定义了`static`静态成员，则整个继承体系里面只有一个这样的成员，无论派生出多少子类，都只有一个`static`成员实列。

  ## 菱形继承

  **菱形继承：菱形继承是多继承的一种特殊情况。**

  **菱形继承的问题：菱形继承会造成数据冗余和二义性问题。**

  ### 虚继承

  ​	虚继承是用来解决菱形继承出现的二义性和数据冗余，虚继承需要到菱形继承的中间父类来进行虚继承才可解决菱形继承问题。

  ​	**使用案列：**

  ```cpp
  #include <iostream>
  
  class A
  {
  public:
  	//A(int a = 10)
  	//{
  	//	_a = a;
  	//}
  private:
  	int _a = 1;
  };
  
  class B : virtual public A
  {
  public:
  	//B(int b = 20)
  	//	:A::A(100)
  	//{
  	//	_b = b;
  	//}
  private:
  	int _b = 2;
  };
  
  class C : virtual public A 
  {
  private:
  	int _c = 3;
  };
  
  class D : public B, public C
  {
  private:
  	int _d = 4;
  };
  
  void Test1(void)
  {
  	A a;
  	B b;
  	a = b;
  	A* pa = &b;
  	A& ra = b;
  }
  
  void Test2(void)
  {
  	D d;
  }
  
  int main(void)
  {
  	Test2();
  	//Test1();
  
  
  	return 0;
  }
  ```

  ### 继承的总结

  1. 很多人说C++语法复杂，其实多继承就是一个体现，有了多继承就存在菱形继承，有了菱形继承就有虚拟继承，底层实现就很复杂，所以一般不建议设计出多继承，否则在复杂及性能上都有问题。

  2. 多继承可以认为是C++的缺陷直以，很多后来的xx语言都没有多继承，比如java。

  3. 继承和组合

     + `public`继承是一种is-a的关系，也就是说每个派生类对象都是一个基类对象。

     + 组合式一种has-a的关系，假设B组合了A，每个B对象中都有一个A对象。

     + [优先使用对象组合而不是类继承]([优先使用对象组合，而不是类继承 - 残雪余香 - 博客园 (cnblogs.com)](https://www.cnblogs.com/nexiyi/archive/2013/06/16/3138568.html))

     + 继承允许你根据基类的实现来定义派生类的实现，这种通过生成派生类的复用通常被称之为白箱复用（white-box reuse）。术语“白箱”是相对可视性而言：在继承方式中，基类的内部细节对子类可见。

       继承一定程度破坏了基类的封装，基类的改变对派生类有很大的影响，派生类和基类的依赖关系很强，耦合度很高。

     + 对象组合是类继承之外的另一种复用手段，新的更复杂的功能可以通过组合或组装对象来获得，对象组合要被组合的对象具有良好的定义的接口，这种你服用风格被称之为黑箱复用（black-box reuse），因为对象的内部细节是不可见的对象只以“黑箱”的形式出现。

       组合类之间没有很强的依赖关系，耦合度很低，优先使用对象组合有助于你保持每个类被封装。

     + 实际尽量多去用组合，组合的耦合度很低，代码维护性好，不过继承也有用武之地的，有些关系就适合继承那就用继承，另外要实现多态也必须要继承。类之间的关系可以用继承，可以用组合就用组合。

     

     

     # 多态

     ## 多态的概念

     ​	**多态的概念：通俗来讲就是多种形态，不同对象进行同一个任务会有不同的结果，这就是多态。**

  ## 多态的构成条件

  ​	多态是在不同继承关系的类对象，去调用同一函数，产生了不同的行为。

  ​	那么在继承中要构成多态还有两个条件：

  1. 必须通过基类的指针或引用调用虚函数
  2. 被调用的函数必须是虚函数且派生类必须对基类的虚函数进行重写

  ## 虚函数

  ​	**虚函数：被`virtual`修饰的类成员函数称为虚函数。**

  ## 虚函数的重写

  虚函数的重写（覆盖）：派生类中有一个跟基类完全相同的虚函数（即派生类虚函数与基类虚函数的返回值类型、函数名字和参数列表完全相同），称子类的虚函数重写了父类的虚函数。

  **使用案列：**

  ```cpp
  #include <iostream>
  #include <string>
  
  class People
  {
  public:
  	//虚函数的定义
  	virtual void Func(void)
  	{
  		std::cout << "普通人——全价票" << std::endl;
  	}
  private:
  	std::string sex;
  	short age;
  };
  
  class Students : public People
  {
  public:
  	//子类重写父类的虚函数
  	virtual void Func(void)
  	{
  		std::cout << "学生——半价票" << std::endl;
  	}
  };
  
  
  class Soldier : public People
  {
  public:
  	//子类重写父类的虚函数
  	virtual void Func(void)
  	{
  		std::cout << "军人——优先购票" << std::endl;
  	}
  };
  
  void Test1(People& rp)
  {
  	rp.Func();
  }
  
  int main(void)
  {
  	People p;
  	Students s;
  	Soldier so;
  
  	Test1(p);
  	Test1(s);
  	Test1(so);
  
  	return 0;
  }
  ```

  **注意：如果继承的父类函数是虚函数那么之类可以不用加`virtual`也可以重写**

### 虚函数重写的两个列外

1. 协变（基类于派生类虚函数返回类型不同）

   派生类重写基类虚函数时与基类虚函数返回值类型不同。即基类虚函数返回基类对象的指针或引用，派生类虚函数返回派生类对象的指针或引用时，称之为协变。

   **使用案列：**

   ```cpp
   #include <iostream>
   #include <string>
   
   class A
   {
   public:
   	virtual A& Func(void)
   	{
   		std::cout << "A" << std::endl;
   
   		return *this;
   	}
   };
   
   class B : public A
   {
   public:
   	virtual B& Func(void)
   	{
   		std::cout << "B" << std::endl;
   
   		return *this;
   	}
   };
   
   void Test(A& a)
   {
   	a.Func();
   }
   
   int main(void)
   {
   	A a;
   	B b;
   
   	Test(a);
   	Test(b);
   
   	return 0;
   }
   ```

2. 析构函数的重写（基类与派生类析构函数的名字不同）

   如果基类的析构函数为虚函数，此时派生类析构函数只要定义，无论是否加`virtual`关键字，都与基类的析构函数重写，虽然基类与派生类析构函数名字不同。虽然函数名不同，看起来违背了重写的规则，其实不然这里可以理解为编译器对析构函数的名称做了特殊处理，编译后析构函数的名称统一处理成`destructor`。

   **使用案列：**

   ```cpp
   #include <iostream>
   #include <string>
   
   class A
   {
   public:
   	virtual ~A(void)
   	{
   		std::cout << "~A" << std::endl;
   	}
   };
   
   class B : public A
   {
   public:
   	virtual ~B(void)
   	{
   		std::cout << "B" << std::endl;
   	}
   };
   
   int main(void)
   {
   	A* pa = new A;
   	A* pb = new B;
   
   	delete pa;
   	delete pb;
   
   	return 0;
   }
   ```

   



### 抽象类

#### 概念

​	在虚函数的后面写上=0，则这个函数为纯虚函数，包含纯虚函数的类叫做抽象类（也叫接口类），抽象类不能实列化出对象。

派生类继承后野不能直接实列化出对象，只有重写了纯虚函数，派生类才能实列化出对象，纯虚函数规范了派生类必须重写，另外纯虚函数更体现了接口继承。

**使用案列：**

```cpp
#include <iostream>
#include <string>

class A
{
public:
	virtual void Test(void) = 0
	{
		std::cout << "A" << std::endl;
	}
};

class B : public A
{
public:
	virtual void Test(void)
	{
		std::cout << "B" << std::endl;
	}
};

int main(void)
{
	A* pb = new B;
	pb->Test();

	return 0;
}
```



#### 接口的继承和实现继承

普通函数的继承是一种实现继承，派生类继承了基类函数，可以使用函数继承的是函数的实现。

虚函数的继承是一种接口继承，派生类继承的是基类虚函数接口，目的是为了重写达成多态继承是接口。

所以如果不实现多态，不要把函数定义成虚函数。



# 🥗🥗🥗单列模式

单列模式是一种程序设计模式，当某个场景全局只能有一个对象时，我们这时就会用到单列模式来设计程序。

那么怎么保证全局只能有一个对象呢？这时我们可以定义个静态的类成员指针且把改类的默认构造函数定义为私有，拷贝构造和赋值重载禁用这时改成员变量只能同过`new`来创建一个对象而不能直接定义一个对象这就保证了全局只能有一个对象。

## 饿汉模式

饿汉模式成员函数初始化只能在`main`函数开始之前初始化，这就保证了全局只有一个对象。

```cpp
//饿汉模式
class Singleton
{
private:
	Singleton()
		:_a(0)
	{};

	Singleton(const Singleton&) = delete;
	Singleton& operator=(const Singleton&) = delete;

	size_t _a;
	static Singleton* _inst;

public:
	static Singleton* GetInstance(void)
	{
		return _inst;
	}
};

Singleton* Singleton::_inst = new Singleton;
```

## 懒汉模式

懒汉模式是用来解决进程启动慢的问题，因为饿汉模式要在进入`main`函数之前初始化如果初始化对象过大会导致进入`main`函数时间过久用户体验不太好。

```cpp
//懒汉模式
class Singleton
{
private:
	Singleton()
		:_a(0)
	{};

	Singleton(const Singleton&) = delete;
	Singleton& operator=(const Singleton&) = delete;

	size_t _a;
	static Singleton* _inst;
	static std::mutex _mut;

public:
	static Singleton* GetInstance(void)
	{
		if (nullptr == _inst)
		{
			_mut.lock();

			if (nullptr == _inst)
			{
				_inst = new Singleton;
			}

			_mut.unlock();
		}
		return _inst;
	}
};

std::mutex Singleton::_mut;

Singleton* Singleton::_inst = nullptr;
```

# C++11

## Lambda表达式

 
