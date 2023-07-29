[TOC]

# STL

## 什么是STL？

> STL(standard template libarary-标准模板库)：是C++标准库的重要组成部分，不仅是一个可复用的组件库，而且里面是一个包罗数据结构与算法的软件框架。

## STL的版本

> + 原始版本
>
>   ​	Alexander Stepanov、Meng Lee在惠普实验室完成的原始版本，秉持着开源精神他们声明允许任何人任意运用、拷贝、修改、传播、商业使用这些代码，无需付费。
>
>   ​	唯一的条件就是也需要向原始版本一样做开源使用，HP版本所有STL版本的始祖。
>
> + P.J.版本
>
>   ​	由P.J. Plauger开发，继承自HP版本，被`Windows Visual C++`采用，不能公开或修改，缺陷：可读性比较低，符号命名比较怪异。
>
> + RW版本
>
>   ​	由Rouge Wage公司开发，继承自HP版本被`C++ Builder`采用，不能公开或修改，可读性一般。
>
> + SGI版本
>
>   ​	由Silicon Graphics Computer Systems，Inc公司开发，继承自HP版本被GCC(Liunx)采用，可移植性好，可公开、修改甚至贩卖，从命名风格和编程风格上看，阅读性非常高。

## STL的六大组件

![image-20220324103951739](https://cdn.jsdelivr.net/gh/ls02/Image/img/202211012004615.png)

## STL的缺陷

> 1. STL库的更新太慢了，上一版本靠谱的是C++98，中间的C++03基本一些修订。C++11出来已经相隔13年，STL才进一步更新。
> 2. STL到现在都没有支持线程安全，并发环境下需要我们自己加锁，且锁的粒度是比较大的。
> 3. STL极度的追求效率，导致内部结构比较复杂。比如：类型萃取，迭代器萃取。
> 4. STL的使用会有代码膨胀问题，比如：使用vector/vetctor/vector这样会生成多份代码，当然这是模板语法本身导致的。

## 容器

### string类

> 1. 字符串是表示字符序列的类。
> 2. 标准的字符串提供了对此类对象的支持，其接口类似于标准字符容器的接口，但添加了专门用于操作单字符字符串的设计特性。
> 3. `string`类是使用`char`（即作为它的字符类型，使用它的默认`char_traits`和适配器类型（关于模板的更多信息，请参阅`basic_string`）。
> 4. `string`类是`basic_string`模板类的一个实列，它使用`char`来实列化`basic_string`模板类，并使用`char_traits`和`allocator`作为`basic_string`的默认参数（更多的模板信息请参考`basic_string`）。
> 5. 注意，这个类独立于所使用的编码来处理字节，如果用来处理多字节或变长字符（而不是实际编码的字符）来操作。
>
> **总结：** 
>
> 1. `string`是表示字符串的字符串类
> 2. 该类的接口与常规容器的接口基本相同，再添加了一些专门用来操作`string`的常规操作。
> 3. `string` 在底层实际是：`basic_string` 模板类的别名，`typedef basic_string<char,char_traits,allocator>string`；
> 4. 不能操作多字节或者变长字符的序列。
>
> 在使用`string`类时，必须包含`#include`头文件以及`using namespace std;`

### string类的成员

#### 成员变量

```cpp
private:
    char* _str;//字符串
    size_t _size;//记录字符串的实际个数
    size_t _capacity;//表示该字符串的容量
    static const size_t npos;//该值是默认-1，该成员可有可无
```

#### 成员函数

##### 默认构造函数

> 由于字符串本质是一个存储字符型的顺序表，所以我们在初始化时只需在末尾多加一个`\0`来作为该字符串的结尾即可。
>
> ```cpp
> /*
> 	参数1：接收一个字符串（该参数是缺省参数如果没有值，那么默认开辟的空间是0，实际容量是1因为要存放\0
> */
> 
> //默认构造函数
> string(const char* str = "")
>     //动态申请一个字符串大小的容量，+1是用来存放\0
>     :_str(new char[strlen(str) + 1])
>         //初始化字符串实际个数
>         , _size(strlen(str))
>         //初始化当前容量，该容量不会记录\0
>         , _capacity(strlen(str))
>     {
>         //把str值拷贝过去完成初始化
>         strcpy(_str, str);
>     }
> ```

##### 拷贝构造

> 由于每个字符串都需要动态申请来存储，那么就不能使用浅拷贝，需要进行深拷贝。
>
> 当前的拷贝构造实现的深拷贝是用现代方法来完成的深拷贝，现代方法利用了默认构造的特性来完成。
>
> 我们创建一个临时对象，该临时对象的`_str`是动态申请而来的，所以我们不用担心出了栈就会消失，如此一来我们就可以把临时对象的`_str`和`this`对线的`_str`地址进行交换，而在交换前我们要确保`this`的`_str`是被初始化成`nullptr`的，因为临时对象在出栈的一瞬间会调用它的析构进行的资源清理。
>
> 如果`this._str`未初始化的话是野指针，如果对野指针释放会发生内存错误，而如果是`nullptr`的话`delete`释放时是会忽略而什么都不做，因为`delete`内对空指针进行了判断。
>
> 当上述操作完成后我们再把`str`对象的数据拷贝过来即可完成深拷贝，现代写法的拷贝构造利用了默认构造的特性来完成不主动动态内存申请。
>
> ```cpp
> //拷贝构造现代写法,利用默认构造函数申请空间，再把this对象的空间和temp默认构造申请的空间交换
> //从而达到深拷贝的目的
> string(const string& s)
>     //由于会调用析构，如果不初始化成nullptr会释放不属于自己的空间会出错，
>     //如果对释放nullptr则什么都不做，因为delete内对nullptr有判断
>     :_str(nullptr)
>     {
>         //利用temp调用默认构造函数
>         string temp(s._str);
>         //把nullptr和temp交换
>         swap(temp);
>     }
> ```



##### 赋值重载

> 赋值重载也需要进行深拷贝，而我们用的现代写法是利用了拷贝构造，拷贝构造再利用默认构造来完成深拷贝（默认构造：我真就是究极打工仔呗，帮你申请完内存还得帮你清理垃圾）。
>
> **现代写法的优缺点：**
>
> + 优点
>
>   代码简洁
>
> + 缺点
>
>   自己给赋值无法处理，会导致内存空间变换，一般影响不大如果介意可以考虑用传统写法。
>
> 由于赋值重载的参数是传值传参所以会发生一次拷贝构造，而拷贝构造又会调用默认构造来完成动态内存申请。
>
> 当完成者一系列的操作，当前的`s`对象的动态内存并不是外面哪一个而是通过默认构造出来的新的动态内存。
>
> 如此一来该对象`s._str`不就是我们`this._str`想要的东西吗？
>
> 我们直接一交换就完成了深拷贝。
>
> ```cpp
> //赋值重载，编译器生成的无法满足需求需要自己写
> //现代写法，利用拷贝构造完成内存申请，再和this一交换即可完成内存的申请
> //由于赋值重载一般都是经过默认构造所以不用担心随机值问题
> string& operator=(string s)
> {
>     swap(s);
> 
>     return *this;
> }
> ```

##### 析构函数

> 由于`string`类是向系统申请了内存，所以我们编译器生成的析构是无法满足我们的需求了，我们需要自行编写逻辑来完成资源的清理。
>
> ```cpp
> //析构函数
> ~string()
> {
>     delete[] _str;
>     _str = nullptr;
>     _size = 0;
>     _capacity = 0;
> }
> ```

#### 插入接口

##### insert接口

> `insert`接口可以对任何形式的字符串进行插入，`insert`插入时我们需要把`pos`位置到`str.size()`位置进行往后挪`n`，当完成挪动我们只需把说数据覆盖上去即可，如果`pos`位置是`size()`那么我们直接把`str`的所有数据拷贝到`this._str`后面。
>
> 当完成`insert`插入那么其它所有插入直接调用该接口即可。
>
> `insert`**代码实现：**
>
> ```cpp
> //插入接口
> //任意位置插入
> string& insert(size_t pos, const string& str)
> {
>     assert(pos <= _size);
>     size_t len = str.size();
>     if (_size + len >= _capacity)
>     {
>         reserve(_size + len);
>     }
> 
>     //中间和头插
>     if (pos < _size)
>     {
>         size_t end = _size + 1;
>         while (end > pos)
>         {
>             _str[end + len - 1] = _str[end - 1];
>             end--;
>         }
> 
>         strncpy(_str + pos, str._str, str._size);
>     }
>     //尾插
>     else
>     {
>         strcpy(_str + _size, str._str);
>     }
> 
>     _size += len;
> 
>     return *this;
> }
> 
> string& insert(size_t pos, const char* s)
> {
>     assert(pos <= _size);
> 
>     size_t len = strlen(s);
>     if (_size + len >= _capacity)
>     {
>         reserve(_size + len);
>     }
> 
>     //中间和头插
>     if (pos < _size)
>     {
>         size_t end = _size + 1;
>         while (end > pos)
>         {
>             _str[end + len - 1] = _str[end - 1];
>             end--;
>         }
> 
>         strncpy(_str + pos, s, len);
>     }
>     //尾插
>     else
>     {
>         strcpy(_str + _size, s);
>     }
> 
>     _size += len;
> 
>     return *this;
> }
> 
> string& insert(size_t pos, const char* s, size_t n)
> {
>     assert(pos <= _size);
> 
>     size_t len = n;
>     if (len > strlen(s))
>     {
>         len = strlen(s);
>     }
> 
>     if (_size + len >= _capacity)
>     {
>         reserve(_size + len);
>     }
> 
>     //中间和头插
>     if (pos < _size)
>     {
>         size_t end = _size + 1;
>         while (end > pos)
>         {
>             _str[end + len - 1] = _str[end - 1];
>             end--;
>         }
> 
>         strncpy(_str + pos, s, len);
>     }
>     //尾插
>     else
>     {
>         strncpy(_str + _size, s, len);
>     }
> 
>     _size += len;
>     _str[_size] = 0;
>     return *this;
> }
> 
> string& insert(size_t pos, const char ch)
> {
>     assert(pos <= _size);
> 
>     if (_size >= _capacity)
>     {
>         reserve(_size * 2);
>     }
> 
>     size_t end = _size + 1;
>     while (end > pos)
>     {
>         _str[end] = _str[end - 1];
>         end--;
>     }
> 
>     _str[pos] = ch;
>     _size++;
> 
>     return *this;
> }
> 
> string& insert(size_t pos, const char ch, size_t n)
> {
>     assert(pos <= _size);
> 
>     size_t len = n;
>     if (_size + len >= _capacity)
>     {
>         reserve(_size + len);
>     }
> 
>     size_t end = _size + 1;
>     while (end > pos)
>     {
>         _str[end + len - 1] = _str[end - 1];
>         end--;
>     }
> 
>     memset(_str + pos, ch, len);
>     _size += len;
> 
>     return *this;
> }
> ```

##### push_back接口

> 字符串尾插一个字符。
>
> **代码实现：**
>
> ```cpp
> //尾插一个字符
> void push_back(const char ch)
> {
>     insert(_size, ch);
> }
> ```

##### append接口

> 尾插一个`string`类或字符串。
>
> **代码实现：**
>
> ```cpp
> //尾部插入一个类
> string& append(const string& str)
> {
>     insert(_size, str);
> 
>     return *this;
> }
> //尾插一个字符串
> string& append(const char* s)
> {
>     insert(_size, s);
> 
>     return *this;
> }
> ```



##### +=重载

> 尾插一个字符串、`string`类或字符。
>
> **代码实现：**
>
> ```cpp
> //+=重载
> string& operator+=(const string& str)
> {
>     insert(_size, str);
> 
>     return *this;
> }
> 
> string& operator+=(const char* s)
> {
>     insert(_size, s);
> 
>     return *this;
> }
> 
> string& operator+=(const char ch)
> {
>     insert(_size, ch);
> 
>     return *this;
> }
> ```

#### 删接口

##### erase接口

> 从`pos`位置开始`len`个字符，删除前要计算好删除的区间，直接把后面的数据往前覆盖即可，如果`len`大于`size()`那么就是全删直接把`_size`置0并且`_str[_size]`赋值成`'\0`。
>
> **代码实现：**
>
> ```cpp
> //删接口
> //任意位置删除
> string& erase(size_t pos, size_t len = npos)
> {
>     assert(pos < _size);
> 
>     //求出pos位置后面的长度
>     size_t leftLen = _size - pos;
> 
>     //如果该长度和len相等或大于说明是全删
>     if (len >= leftLen)
>     {
>         _size = pos;
>         _str[_size] = 0;
>     }
>     //否则就是删除部分
>     else
>     {
>         //我们把后面的数据往前覆盖即可
>         strcpy(_str + pos, _str + len + pos);
>         _size -= len;
>     }
> 
>     return *this;
> }
> ```

##### pop_back接口

> 该字符串尾删一个字符。
>
> **代码实现：**
>
> ```cpp
> //尾删一个字符
> void pop_back(void)
> {
>     if (_size > 0)
>     {
>         _size--;
>     }
> }
> ```



#### 查找接口

##### find接口

> 查找一个字符或查找也给字串的下标，查找子串我们用`strstr`来完成，而查找找字符遍历即可。
>
> **代码实现：**
>
> ```cpp
> //查找接口
> //找一个字符
> size_t find(const char ch, size_t pos = 0)
> {
>     assert(pos < _size);
> 
>     for (int i = 0; i < _size; i++)
>     {
>         if (_str[i] == ch)
>         {
>             return i;
>         }
>     }
> 
>     return npos;
> }
> 
> size_t find(const char* s, size_t pos = 0)
> {
>     char* index = strstr(_str + pos, s);
> 
>     if (nullptr != index)
>     {
>         return index - _str;
>     }
>     else
>     {
>         return npos;
>     }
> }
> ```

#### 改接口

##### []重载

> 我们只需返回当前位置的引用即可。
>
> **代码实现：**
>
> ```cpp
> //改接口
> //下标重载
> //只读
> const char& operator[](size_t i)const
> {
>     assert(i < _size);
> 
>     return _str[i];
> }
> ```

#### 扩容

##### resize接口

> 修改字符串的实际个数，如果修改的值超越当前容量那么会发生扩容，改扩容多出来的空间会默认给`val`而没传参的话默认补充`\0`。
>
> **修改大小有三种情况：**
>
> 1. 缩容
> 2. 增容但没超过容量
> 3. 增容但超过容量
>
> 2和3我们可以当成一种情况处理，我们只需添加一个检查是否扩容的判断即可完成2和3的需求。而1则更简单了，直接修改`_size`即可不用填充任何数据。
>
> **代码实现：**
>
> ```cpp
> //增加size大小
> void resize(size_t n, const char val = 0)
> {
>     //如果n小于当前大小说明是缩容，容量不动动大小
>     if (n < _size)
>     {
>         _size = n;
>         _str[_size] = 0;
>     }
>     else
>     {
>         //检查是否需要扩容
>         if (n >= _capacity)
>         {
>             reserve(n);
>         }
> 
>         for (size_t i = _size; i < n; i++)
>         {
>             _str[i] = val;
>         }
> 
>         _size = n;
>         //最后一个元素设定为'\0'
>         _str[_size] = 0;
>     }
> }
> ```

##### reserve接口

> 扩充容量如果`n`＞总容量， 那么需要重新申请一块连续的空间。
>
> 我们先申请好容量再把内存的数据拷贝到新申请的内存上，再释放旧空间再把新申请的空间重新赋值给`_str`即可。
>
> **代码实现：**
>
> ```cpp
> //扩容
> void reserve(size_t n = 0)
> {
>     //如果不相等或大于容量那么没必要扩容
>     if (n > _capacity)
>     {
>         char* temp = new char[n + 1];
>         strncpy(temp, _str, _size + 1);
>         delete _str;
> 
>         _str = temp;
>         _capacity = n;
>     }
> }
> ```

#### 输入输出重载

##### <<重载

> 我们需要定义成全局函数，来完成输出重载。
>
> **代码实现：**
>
> ```cpp
> std::ostream& operator<<(std::ostream& out, const string& s)
> {
>     for (auto ch : s)
>     {
>         out << ch;
>     }
> 
>     return out;
> }
> ```

##### >>重载

> 实现基本数据类型的读取。
>
> **代码实现：**
>
> ```cpp
> std::istream& operator>>(std::istream& in, string& s)
> {
>     s.clear();
> 
>     int ch = in.get();
>     while (ch != ' ' && ch != '\n')
>     {
>         s += ch;
>         ch = in.get();
>     }
> 
>     return in;
> }
> ```

##### getline接口

> 接收一行字符，直到遇到`\n`结束。
>
> **代码实现：**
>
> ```cpp
> std::istream& getline(std::istream& in, string& s)
> {
>     s.clear();
> 
>     int ch = in.get();
>     while (ch != '\n')
>     {
>         s += ch;
>         ch = in.get();
>     }
> 
>     return in;
> }
> ```

### string类的源代码

```cpp
#pragma once
#ifndef __STRING_H__
#define __STRING_H__
#include <string.h>
#include <iostream>
#include <algorithm>
#include <assert.h>

namespace ls
{
	class string
	{
	private:
		char* _str;
		size_t _size;
		size_t _capacity;
		static const size_t npos;

	public:
		//迭代器
		typedef char* iterator;
		typedef const char* const_iterator;

		iterator begin(void)
		{
			return _str;
		}

		const_iterator begin(void)const
		{
			return _str;
		}

		iterator end(void)
		{
			return _str + _size;
		}

		const_iterator end(void)const
		{
			return _str + _size;
		}

		//默认构造函数
		string(const char* str = "")
			:_str(new char[strlen(str) + 1])
			, _size(strlen(str))
			, _capacity(strlen(str))
		{
			strcpy(_str, str);
		}

		//拷贝构造现代写法,利用默认构造函数申请空间，再把this对象的空间和temp默认构造申请的空间交换
		//从而达到深拷贝的目的
		string(const string& s)
			//由于会调用析构，如果不初始化成nullptr会释放不属于自己的空间会出错，
			//如果对释放nullptr则什么都不做，因为delete内对nullptr有判断
			:_str(nullptr)
		{
			//利用temp调用默认构造函数
			string temp(s._str);
			//把nullptr和temp交换
			swap(temp);
		}

		//赋值重载，编译器生成的无法满足需求需要自己写
		//现代写法，利用拷贝构造完成内存申请，再和this一交换即可完成内存的申请
		//由于赋值重载一般都是经过默认构造所以不用担心随机值问题
		string& operator=(string s)
		{
			swap(s);

			return *this;
		}

		//扩容
		void reserve(size_t n = 0)
		{
			//如果不相等或大于容量那么没必要扩容
			if (n > _capacity)
			{
				char* temp = new char[n + 1];
				strncpy(temp, _str, _size + 1);
				delete _str;

				_str = temp;
				_capacity = n;
			}
		}

		//增加size大小
		void resize(size_t n, const char val = 0)
		{
			//如果n小于当前大小说明是缩容，容量不动动大小
			if (n < _size)
			{
				_size = n;
				_str[_size] = 0;
			}
			else
			{
				//检查是否需要扩容
				if (n >= _capacity)
				{
					reserve(n);
				}

				for (size_t i = _size; i < n; i++)
				{
					_str[i] = val;
				}

				_size = n;
				//最后一个元素设定为'\0'
				_str[_size] = 0;
			}
		}

		//插入接口
		//任意位置插入
		string& insert(size_t pos, const string& str)
		{
			assert(pos <= _size);
			size_t len = str.size();
			if (_size + len >= _capacity)
			{
				reserve(_size + len);
			}

			//中间和头插
			if (pos < _size)
			{
				size_t end = _size + 1;
				while (end > pos)
				{
					_str[end + len - 1] = _str[end - 1];
					end--;
				}

				strncpy(_str + pos, str._str, str._size);
			}
			//尾插
			else
			{
				strcpy(_str + _size, str._str);
			}

			_size += len;

			return *this;
		}

		string& insert(size_t pos, const char* s)
		{
			assert(pos <= _size);

			size_t len = strlen(s);
			if (_size + len >= _capacity)
			{
				reserve(_size + len);
			}

			//中间和头插
			if (pos < _size)
			{
				size_t end = _size + 1;
				while (end > pos)
				{
					_str[end + len - 1] = _str[end - 1];
					end--;
				}

				strncpy(_str + pos, s, len);
			}
			//尾插
			else
			{
				strcpy(_str + _size, s);
			}

			_size += len;

			return *this;
		}

		string& insert(size_t pos, const char* s, size_t n)
		{
			assert(pos <= _size);

			size_t len = n;
			if (len > strlen(s))
			{
				len = strlen(s);
			}

			if (_size + len >= _capacity)
			{
				reserve(_size + len);
			}

			//中间和头插
			if (pos < _size)
			{
				size_t end = _size + 1;
				while (end > pos)
				{
					_str[end + len - 1] = _str[end - 1];
					end--;
				}

				strncpy(_str + pos, s, len);
			}
			//尾插
			else
			{
				strncpy(_str + _size, s, len);
			}

			_size += len;
			_str[_size] = 0;
			return *this;
		}

		string& insert(size_t pos, const char ch)
		{
			assert(pos <= _size);

			if (_size >= _capacity)
			{
				reserve(_size * 2);
			}

			size_t end = _size + 1;
			while (end > pos)
			{
				_str[end] = _str[end - 1];
				end--;
			}

			_str[pos] = ch;
			_size++;

			return *this;
		}

		string& insert(size_t pos, const char ch, size_t n)
		{
			assert(pos <= _size);

			size_t len = n;
			if (_size + len >= _capacity)
			{
				reserve(_size + len);
			}

			size_t end = _size + 1;
			while (end > pos)
			{
				_str[end + len - 1] = _str[end - 1];
				end--;
			}

			memset(_str + pos, ch, len);
			_size += len;

			return *this;
		}

		//尾插一个字符
		void push_back(const char ch)
		{
			insert(_size, ch);
		}

		//尾部插入一个类
		string& append(const string& str)
		{
			insert(_size, str);

			return *this;
		}
		//尾插一个字符串
		string& append(const char* s)
		{
			insert(_size, s);

			return *this;
		}

		//+=重载
		string& operator+=(const string& str)
		{
			insert(_size, str);

			return *this;
		}

		string& operator+=(const char* s)
		{
			insert(_size, s);

			return *this;
		}

		string& operator+=(const char ch)
		{
			insert(_size, ch);

			return *this;
		}
		
		//查找接口
		//找一个字符
		size_t find(const char ch, size_t pos = 0)const
		{
			assert(pos < _size);

			for (size_t i = 0; i < _size; i++)
			{
				if (_str[i] == ch)
				{
					return i;
				}
			}

			return npos;
		}

		size_t find(const char* s, size_t pos = 0)c
		{
			char* index = strstr(_str + pos, s);

			if (nullptr != index)
			{
				return index - _str;
			}
			else
			{
				return npos;
			}
		}

		//改接口
		//下标重载
		//只读
		const char& operator[](size_t i)const
		{
			assert(i < _size);

			return _str[i];
		}
		//可读可写
		char& operator[](size_t i)
		{
			assert(i < _size);

			return _str[i];
		}

		//删接口
		//任意位置删除
		string& erase(size_t pos, size_t len = npos)
		{
			assert(pos < _size);
			
			//求出pos位置后面的长度
			size_t leftLen = _size - pos;

			//如果该长度和len相等或大于说明是全删
			if (len >= leftLen)
			{
				_size = pos;
				_str[_size] = 0;
			}
			//否则就是删除部分
			else
			{
				//我们把后面的数据往前覆盖即可
				strcpy(_str + pos, _str + len + pos);
				_size -= len;
			}

			return *this;
		}

		//尾删一个字符
		void pop_back(void)
		{
			if (_size > 0)
			{
				_size--;
			}
		}

		//清除字符串
		void clear(void)
		{
			_size = 0;
			_str[_size] = 0;
		}

		//获取实际个数
		size_t size(void)const
		{
			return _size;
		}

		//检查是否为空串
		bool empty(void)const
		{
			return _size == 0;
		}

		//获取容量大小
		size_t capacity(void)const
		{
			return _capacity;
		}

		void swap(string& s)
		{
			std::swap(_str, s._str);
			_size = s._size;
			_capacity = s._capacity;
		}

		const char* c_str(void)const
		{
			return _str;
		}

		//析构函数
		~string()
		{
			delete[] _str;
			_str = nullptr;
			_size = 0;
			_capacity = 0;
		}
	};

	const size_t ls::string::npos = -1;

	inline bool operator<(const string& s1, const string& s2)
	{
		return strcmp(s1.c_str(), s2.c_str()) < 0;
	}

	inline bool operator==(const string& s1, const string& s2)
	{
		return strcmp(s1.c_str(), s2.c_str()) == 0;
	}
	
	inline bool operator!=(const string& s1, const string& s2)
	{
		return !(s1 == s2);
	}

	inline bool operator<=(const string& s1, const string& s2)
	{
		return s1 < s2 || s1 == s2;
	}

	inline bool operator>(const string& s1, const string& s2)
	{
		return !(s1 <= s2);
	}

	inline bool operator>=(const string& s1, const string& s2)
	{
		return !(s1 < s2);
	}

	std::ostream& operator<<(std::ostream& out, const string& s)
	{
		for (auto ch : s)
		{
			out << ch;
		}
		
		return out;
	}


	std::istream& operator>>(std::istream& in, string& s)
	{
		s.clear();

		int ch = in.get();
		while (ch != ' ' && ch != '\n')
		{
			s += ch;
			ch = in.get();
		}

		return in;
	}

	std::istream& getline(std::istream& in, string& s)
	{
		s.clear();

		int ch = in.get();
		while (ch != '\n')
		{
			s += ch;
			ch = in.get();
		}

		return in;
	}
}
#endif
```

### vector类

> `vector`是一个动态的数组，该数组能存储任何类型的数据。

### vector类的成员

#### vector成员变量

> ```cpp
> private:
> //数据起始地址
> T* _start;
> //有效数据的最后一个元素的下一个位置
> T* _finish;
> //容量，不过是用地址表示
> T* _endOfStorage;
> ```
>
> 顺序表的管理我采用三个指针来进行管理，**如下图：**
>
> ![image-20220326154637016](https://cdn.jsdelivr.net/gh/ls02/Image/img/202211042057763.png)

#### vector成员函数

##### 构造函数

> `vector`支持两种构造函数一种是无参的，一种是有参的。
>
> **代码实现:**
>
> ```cpp
> //构造函数
> vector()
>     :_start(nullptr)
>         ,_finish(nullptr)
>         ,_endOfStorage(nullptr)
>     {}
> 
> //构造函数重载
> vector(size_t n, const T& value = T())
>     :_start(nullptr)
>         ,_finish(nullptr)
>         ,_endOfStorage(nullptr)
>     {
>         reserve(n);
> 
>         while (n--)
>         {
>             push_bakck(value);
>         }
>     }
> ```

##### 拷贝构造函数

> 拷贝构造在使用前一定要初始化成`nullptr`.
>
> **代码实现：**
>
> ```cpp
> //拷贝构造
> vector(vector<T>& v)
>     :_start(nullptr)
>         ,_finish(nullptr)
>         ,_endOfStorage(nullptr)
>     {
>         _start = new T[v.capacity()];
> 
>         for (size_t i = 0; i < v.size(); i++)
>         {
>             _start[i] = v._start[i];
>         }
> 
>         _finish = _start + v.size();
>         _endOfStorage = _start + v.capacity();
>     }
> ```



##### 赋值重载

> 赋值重载使用的是现代方法实现的，利用拷贝构造完成对象的创建和深拷贝，再用`this`和`v`即可完成空间的申请。
>
> **代码实现：**
>
> ```cpp
> //赋值重载
> vector<T>& operator=(vector<T> v)
> {
>     //利用拷贝构造完成
>     swap(v);
> 
>     return *this;
> }
> ```

##### 插入接口

###### insert接口

> 在进行插入时，我们需要注意迭代器失效问题，所以我们需要在可能会导致迭代器失效的地方对迭代器完成一次更新。
>
> **代码实现：**
>
> ```cpp
> //任意位置插入
> void insert(iterator pos, size_t value)
> {
>     //检查是否需要扩容
>     if (_finish >= _endOfStorage)
>     {
>         //记录迭代器所在下标
>         size_t len = pos - _start;
>         size_t newCapacity = capacity() ? capacity() * 2 : 4;
>         reserve(newCapacity);
>         //更新迭代器位置，防止迭代器失效
>         pos = _start + len;
>     }
> 
>     iterator end = _finish - 1;
>     while (end >= pos)
>     {
>         *(end + 1) = *end;
>         end--;
>     }
> 
>     *pos = value;
>     _finish++;
> }
> ```

##### 删除接口

###### erase接口

> 注意在删除时需要返回一个更新后的迭代器，如果不返回的话，外面使用迭代器会失效，当然它也可以不用返回值来更新迭代器但是我们最好提供一个返回值，来供它有更多的方法来更新迭代器的位置。
>
> **代码实现:**
>
> ```cpp
> //任意位置删除
> iterator erase(iterator pos)
> {
>     iterator it = pos + 1;
>     while (it != _finish)
>     {
>         *(it - 1) = *it;
>         ++it;
>     }
> 
>     --_finish;
> 
>     return pos;
> }
> ```



##### 扩容接口

> 扩容前我们需要拿一个值记录以下大小，否则我们不能正确的拿到大小，因为我们是用地址来确定大小的，但是重新开辟了一块空间并不能很好的拿到之前的大小，所以大多数人会选择用一个变量来记录。
>
> **代码实现：**
>
> ```cpp
> //扩容
> void reserve(size_t n)
> {
>     if (n > size())
>     {
>         size_t sz = size();
>         T* temp = new T[n];
> 
>         //是否需要拷贝数据
>         if (nullptr != _start)
>         {
>             for (size_t i = 0; i < sz; i++)
>             {
>                 temp[i] = _start[i];
>             }
>         }
> 
>         delete[] _start;
>         _start = temp;
>         _finish = _start + sz;
>         _endOfStorage = _start + n;
>     }
> }
> ```

### vector源代码实现

```cpp
#pragma once
#ifndef __VECTOR_H__
#define __VECTOR_H__
#include <iostream>
#include <assert.h>
#include <algorithm>

namespace ls
{
	template <class T>
	class vector
	{
	private:
		T* _start;
		T* _finish;
		T* _endOfStorage;

	public:
		//迭代器
		typedef T* iterator;
		typedef const T* const_iterator;

		iterator begin(void)
		{
			return _start;
		}

		const_iterator begin(void)const
		{
			return _start;
		}

		iterator end(void)
		{
			return _finish;
		}

		const_iterator end(void)const
		{
			return _finish;
		}

		//构造函数
		vector()
			:_start(nullptr)
			,_finish(nullptr)
			,_endOfStorage(nullptr)
		{}

		//构造函数重载
		vector(size_t n, const T& value = T())
			:_start(nullptr)
			,_finish(nullptr)
			,_endOfStorage(nullptr)
		{
			reserve(n);

			while (n--)
			{
				push_bakck(value);
			}
		}

		//拷贝构造
		vector(vector<T>& v)
			:_start(nullptr)
			,_finish(nullptr)
			,_endOfStorage(nullptr)
		{
			_start = new T[v.capacity()];

			for (size_t i = 0; i < v.size(); i++)
			{
				_start[i] = v._start[i];
			}

			_finish = _start + v.size();
			_endOfStorage = _start + v.capacity();
		}

		//析构函数
		~vector(void)
		{
			if (nullptr != _start)
			{
				delete[] _start;
			}

			_start = _finish = _endOfStorage = nullptr;
		}

		//赋值重载
		vector<T>& operator=(vector<T> v)
		{
			//利用拷贝构造完成
			swap(v);

			return *this;
		}

		//[]重载
		T& operator[](const size_t i)
		{
			return _start[i];
		}

		const T& operator[](const size_t i)const
		{
			return _start[i];
		}

		//增接口
		//尾插一个值
		void push_back(const T& value)
		{
			//检查空间是否满了
			if (_finish >= _endOfStorage)
			{
				size_t newCapacity = capacity() ? capacity() * 2 : 4;
				reserve(newCapacity);
			}

			*_finish = value;
			_finish++;
		}

		//任意位置插入
		void insert(iterator pos, size_t value)
		{
			//检查是否需要扩容
			if (_finish >= _endOfStorage)
			{
				//记录迭代器所在下标
				size_t len = pos - _start;
				size_t newCapacity = capacity() ? capacity() * 2 : 4;
				reserve(newCapacity);
				//更新迭代器位置，防止迭代器失效
				pos = _start + len;
			}

			iterator end = _finish - 1;
			while (end >= pos)
			{
				*(end + 1) = *end;
				end--;
			}
			
			*pos = value;
			_finish++;
		}

		//删接口
		//任意位置删除
		iterator erase(iterator pos)
		{
			iterator it = pos + 1;
			while (it != _finish)
			{
				*(it - 1) = *it;
				++it;
			}

			--_finish;

			return pos;
		}

		//尾删
		void pop_back(void)
		{
			--_finish;
		}

		//扩容
		void reserve(size_t n)
		{
			if (n > size())
			{
				size_t sz = size();
				T* temp = new T[n];
				
				//是否需要拷贝数据
				if (nullptr != _start)
				{
					for (size_t i = 0; i < sz; i++)
					{
						temp[i] = _start[i];
					}
				}

				delete[] _start;
				_start = temp;
				_finish = _start + sz;
				_endOfStorage = _start + n;
			}
		}

		//调整大小
		void resize(size_t n, const T& value = T())
		{
			if (n < size())
			{
				_finish = _start + n;
			}
			else
			{
				if (n >= capacity())
				{
					reserve(n);
				}

				while (_start + n > _finish)
				{
					*_finish = value;
					++_finish;
				}
			}
		}

		void swap(vector<T>& v)
		{
			std::swap(_start, v._start);
			std::swap(_finish, v._finish);
			std::swap(_endOfStorage, v._endOfStorage);
		}

		size_t size(void)const
		{
			return _finish - _start;
		}

		size_t capacity(void)const
		{
			return _endOfStorage - _start;
		}
        
         void clear(void)
		{
			_finish = _start;
		}
	};


	template <class Con>
	void Print(const Con& v)
	{
		typename Con::const_iterator it = v.begin();
		while (it != v.end())
		{
			std::cout << *it << ' ';
			++it;
		}

		std::cout << std::endl;
	}
}

#endif
```

