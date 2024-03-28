# C++嘎嘎(*^_^*)学
## vs studio项目配置
## 头文件
公共区域声明一些函数想在多个cpp中使用
#pragmma once防止多次声明
## debug
### 断点
break point   
断点时会挂起进程，中断  
fn+F9  
逐语句 step into_进入当前代码行函数，如果有的话  
逐过程 step over 执行下一条语句，不进入函数  
跳出step out 跳出当前函数，回到函数调用位置  
黄色箭头表示指向却没执行  
### 内存查找
在debug模式下，未初始化的变量直接给他填满1，这是额外的事情
监视器添加变量  
监视局部变量  
监视auto变量  
调试->视图->窗口->内存->memory1在这里你可以监视到内存里存的是什么
## compiler
### 预编译过程及命令pre-process
#后面跟的都是预处理语句 
const data 放在一起
#### #include  
打开文件copy then paste
编译程序在编译前就找头文件 
#### #if 
条件判断代码是否放入
### 编译阶段compiler
抽象语法树  
一个.cpp文件+include 的translation unit  
编译阶段会发生的错误c开头
## linker
 Link ERROR 
 check 程序入口点entry point，通常是main函数
 找打申明函数的定义是linker做的事情
 linker 还会检查是否有完全相同的函数和变量存在
 ```
 #include<iostream>
void Log(const char* message);


int Multiply(int a, int b)
{  
	Log("Multiply");
	return a*b;
}

int main()
{
	/*std::cout << Multiply(5, 8) << std::endl;*/
	std::cin.get();
}
 ```
 报错因为在该文件中没用到Multiply 不代表将来被其他文件include之后不使用  
 如果能告诉linker 这个Multiply 只在本文件使用就可以消除链接错误了
### complile文件查看
项目-属性-C++-OUTput-汇编程序输出
### 代码优化
```
int Multiply(int a, int b)
{
	int result = a * b;
	return result;
}
	mov	DWORD PTR _result$[ebp], eax
; Line 5
	mov	eax, DWORD PTR _result$[ebp]
```
看到result变量导致了一些无效的汇编代码
### int main fuction 
默认返回0
entry point;
下面代码中<<仅仅表示一个函数like print()
```c++
#include<iostream>

int main(){
    std::cout"hello world"<<std::endl;
    std::cin.get();
}

```

## 基本变量及类型
变量可以用来给数据命名。  
虽然变量有很多基本数据类型  
但这些数据类型的唯一区别是它们所占的内存地址空间的大小  
定义时可以选择是否赋初值  
放在栈或者堆中
### 声明decration??和定义defination
声明：告诉编译器函数和变量名存在
### int 
4B 
unsigned ——>
### char-1B
cout时会把它看成一个字符
### short-2B
### long-usually 4B
### long long
### float-4B
你得在数据后加f/F
### double-8B
### bool-1B
skill:1B for 8 bool
value:true;false;
cout:1/0
### sizeof() 不一定要括号

## 函数 fuction not method
避免代码重复
调用函数时，在系统中会调用call指令   
而且会为该函数建立获得记录放入栈中  
还得压入返回地址

## 条件分支语句conditions branches if
 优化的代码将避免分支，  
 由关系表达式（关系运算）+分支语句复合而成  
 ==->重载为两个整形数比较的关系运算符
 检查指针是否为空NULL=0
 if ptr （！=NULL） 不需要写
 else 什么只在if不满足时才需要额外做的
 ```C++
  else if (ptr == "hello")
		Log("ptr is Hello");
    
//==
else{
    if((ptr == "hello"))
		Log("ptr is Hello");
}
 ```
 else if 不是关键字  
 那如何理解else if后面再加else，难道说C++本身支持多个else么  
 让我用一段代码测试一下
 数学编程，逻辑编程，用数学计算替代if语句
## 循环语句
在显示图片制作游戏  
游戏循环game loop
### for循环
for(变量声明;条件;迭代调用)
第一段：开始for执行一次
第二段 bool 不写默认为true
```C++
for(int i=5;i<5;i++){
    Log("Hello world");
}
//eq
int i=5;
for(;i<5;){
    Log("Hello world");
    i++;
}
//eq
int i=5;
while(i<5){
  Log("Hello world");
    i++;
}
//没啥屌用
do 
{


}
while(condition);
```
本质whlie和for可以做相同的事情，只是约定了当判断条件不变时用while就行
### 控制流语句continue ，break，return
#### continue只用在循环中
进入下一次迭代
#### break出现在循环中，也出现在swith中
跳出循环
#### return 可以用在任意地方
跳出函数
## point 原始指针* &
编程-内存  
指针对内存管理和操作很重要  
指针是一个int（32bit）存放的是地址 逻辑地址吧？？  
void* 指针的类型只是假设这个地址对应的内容的type，用于访问用
```
void* p=0;
```
0不是一个有效的内存地址；因为内存不会到0
&+已存在的变量表示这个变量的地址
我们已经给指针存了一个地址，怎么访问这个地址的数据呢，用*运算符
*+指针变量名
指针的*运算符叫做dereference运算符
### &references 其实本质和指针一样
不占内存空间  
建立了一个a的引用，给a造了一个别名  
```
声明一个引用
int& ref=a;->必须赋值 
```

---
*&作为操作符时  
address->value dereference op*  
value->address reference op&  
一个变量名varname默认为其value  
```

int =5;
int b=8;


//cant do
ref=b;

int* ref=&a;
*ref=2;
ref=&b;
*ref =1;
void Increment(int* value)
{
	(*value)++;
}
	int a = 5;
	Increment(&a);

void Increment(int& value)
{
	value++;
}
	int a = 5;
	Increment(a);
```

## 类和面向对象编程class|struct
只是一种编程方式，但是java、C#只能进行面向对象编程，C又没有入口  
class 类类型的变量名  
由类类型构成的变量称为对象，对象变量称为实例  
类中内容的可见性default-private-public  
方法=在类中的函数-只是语法糖，让代码更好管理
### 与C的对比
//C++中可以直接在结构体里定义初值  
//C++定义对象A前面不用加struct  
//此时只有别名不能定义构造函数  
### 可见性visibility  
private：只有在类|friend类作用域内可以访问  

**hint：私有成员m_前缀表示其为私有成员**  

protect：类+子类可以访问  
public：全局访问  
#### struct&class区别：
##### 技术实现 
只有可见度的区别   
class默认private  
structure 默认public  
使用情况不同只是为了保存向后兼容  
##### 编程风格（编程逻辑角度）
当表示Plain old data POD 喜欢用struct  
eg 数学向量类
```c++
struct vect2{
    float x,y;
    void Add(const vec2& other)
    {
        x+=other.x;
        y+=other.y;
    }
};
```
### 实例化一个类
我们可以选择将实例放在stack||heap  
在C++中我们可以将变量分配到stack上，但是在JAVA中，所有变量都被分配在heap中   
#### stack实例化
stack frame
stack和他的作用域和调用相关  
```C++
Entity s(parameter);
Entity u=Entity(parameter);
```
如果能放在stack就放在stack里
#### heap实例化
一旦你new了，you are actually responsible to free that memory,它不像java会自动处理这些事情 


new创建对象需要指针接收，一处初始化，多处使用  
new创建对象使用完需delete销毁  
new创建对象直接使用堆空间，而局部不用new定义对象则使用栈空间  
```C++
Entity* entity=new Entity(parameter);
(*entity).Getname();
entity->Getname();\\ 与上一语句相同
delete entity;
```
由于entity是一个指针，所以先需要dereference 然后再调用内容  
#### ->运算
见上例
### 构造函数
没有返回值，与类名一致；  
default construct  do noting
在c++中 类成员从不会被初始化；可以重载  
隐藏构造函数private  
当你用new创建heap的时候也会调用construct  
```c++
private Log()
{

}
Log()=delete;
```
copy construct
remove construct
#### 初始化成员
成员初始化列表,成员必须按顺序初始化，有性能上的优化
```c++
class example{
	example(){
		std::cout<<"create a example"<<std::endl;
	}
	example(int 8){
	std::cout<<"create a example with"<<x<<std::endl;
	}
}
struct Entity
{
	int x, y;
	example e;
	Entity():x(1),y(2)
	{
	//这里example创建了两次
		e=example(8);
	}
	Entity():x(1),y(2),e(example(8))|e(8)
	{
	//这里example创建了1次
	}
	static void Print()
	{
		std::cout << x << "," << y << std::endl;
	}
};
```
### 析构函数
销毁对象实例
```c++
~ClassName(){}
```
### 继承
多态性
我可以给Entity 实例附上一个子类的实例
### 虚函数
基类写上virtual，重新建议加上override
需要额外的内存建立vtable去帮助基类映射到正确的函数，查表有性能损失
```c++
class Entity
{
public:
virtual std::string GetName()
{
	return "Entity";
}

};

class Player
{
	private:
	std::string m_name;
	public:
	Player(const std::string& name):m_name(name)
	{}
	std::string Getname()override
	{
		return m_name;
	}

}

int main()
{
	Entity* e=new Entity();
	std::cout<<e->GetName()<<std::endl;
	Player* p=new Player("Cherno");
	std::cout<<p->GetName()<<std::endl;
	std::cin.get();
}
```
#### 纯虚函数 interface
基类实现函数功能是毫无意义的，基类作为接口，确定了子类需要有这个功能，每个子类强制重写  
你希望保证你写的类都有某个方法时你可以定义它
```c++
class Printable
{
public:
	virtual std::string GetClassName()=0；
}
class Entity；public Printable
{
public:
virtual std::string GetName()=0；
		std::string GetClassName()override
		{
			return"Entity";
		}；
};

class Player:public Entity
{
	private:
	std::string m_name;
	public:
	Player(const std::string& name):m_name(name)
	{}
	std::string Getname()override
	{
		return m_name;
	}
	std::string GetClassName()override
		{
			return"PLayer";
		}；

}

int main()
{
	Entity* e=new Player("");
	std::cout<<e->GetName()<<std::endl;
	Player* p=new Player("Cherno");
	std::cout<<p->GetName()<<std::endl;
	std::cin.get();
}
```
## Enum
枚举类型，背后对应的整数数据类型你可以自己定义，在这里只需要使用符号替代整数使用，这有利于我们限制输入范围
## array
a collections of varibles the same type  
访问错误的下标在Debug会发生访问冲突-缺少边界检测
### 在stack中建立

```C++
int main()
{
	int example[5];
	int*ptr =example;

	for(int i=0;i<5;i++)
	//没人写小于等于4，因为这要作小于和等于两个比较
	{
		example[i]=2;
	}
	example[4]=4;
	*(ptr+4)=6;
	*(int*)((char*)ptr+16)=6;
	std::cout<<example<<std::endl;
	std::cin.get();
}
```
### 在heap中建立数组
```c++
int* array=new int[5];
delete[] array;
// 下面代码会找不到size
int count=sizeof(array)/sizeof(int);
//解决方案
static const int size=5;
int  array[size];
```
### 两种建立数组方式的区别
最大的不同是`生命周期`：动态开辟的数组不会随着函数调用结束而被释放  
第二个，动态开辟数组为内存间接访问，不合理分配会导致内存碎片&cache缺失`heap区的数据块可能不在cache中`   

如果可能的话还是不要new了，指针间接访存有性能损失啊  

### 原始数组与数组标准库
C++原始数组，没有边界检测，通过new没法算出开辟的数组大小  

当你在栈上分配数组的时候，编译器必须知道数组的大小  
C++标准库数组，安全但是开销大了点
```c++
#include<array>
std::array<int,5>another;
```
## string
a group of characters ,useful in allocating buffer;
character sets;  
an array of characters;
```C++
const char* name="sjksad";
//你不能修改字符数组中的值
char* name="sjksad";
//未封口
char name[6]={'C','h','e','r','o'}
```
**空终止符00 \0**   
双引号默认为const char* 
ASCII NULL 00

### C++标准库由string类
```c++
#include<string>
std::string a;
```
char array+a bunch of fuctions and manipulate
find()
```c++
include<string>
void print(std::string str)
{
	std::cout <<str<<std::endl;
}
```
这会开辟一个形参单元，这影响效率
如果你只想输出不想改变的话传入const+& 不复制不修改
```c++
include<string>
void print(const std::string& str)
{
	std::cout <<str<<std::endl;
}
```
```c++
//bug
const char name[8]="Che\0rno";
std::cout<<strlen(name)<<std::endl;
console:3
```
>将const char array 传给char* 进行访问是一种未定义行为  

mapc  字符串存在逻辑rom部分中 写在const SEGMENT 中，
在release mod 下这不会成功，debug下直接编译错误
```c++
//c++未定义行为，取决于编译器
char* p="Cherno";
p[2]='a';
// 可以
char p[]="Cherno";
p[2]='a';
```
数组可以是因为创建了个变量
长字符
```c++
//wchar windows 2B linux 4B
const wchar_t* p=L"Cherno";

const char16_t* p=u"Cherno";
const char32_t* p=U"Cherno";
```
string_literals;
```c++
using namespace std::string_literals;
std::string name="HCfa"s+"hejfao";
```
##  C++三元运算符=?:
=?: a suger for if statements
```c++
if(s_level>5)
	s_speed=10;
else
	s_speed =5;

s_speed= s_level>5?10:5;
std::string rank=s_level>10?"Master":"new";
//这里不需要创建临时变量，会更快
TODO 返值优化  
```
## static 数据的共享与保护
### 全局static
表示链接时该函数或者变量只对该translation unit 有用    
它将不会被include到其他translation unit 中  
extern 向外部translation unit找声明  
**尽量给一个cpp文件中的类外变量，全局变量+static关键字；**  
由于是顺序编译，变量定义往上放放最上面？？？
### 局部static
变量的生存期和作用范围
static local variable 允许我们建立一个局部作用范围，却有着整个程序生存期的变量
用于函数counter 
### 类或结构体内
可用于描述一个竞争资源或一个有限的实体，如处理机
类内或结构体内的变量  
share menorys with all instances in the class   
static mathod 不会自动获取类实例的隐藏变量，只能抓到静态变量
```c++
//错误代码 勿Q
#include<iostream>
struct Entity
{
	int x, y;

	static void Print()
	{
		std::cout << x << "," << y << std::endl;
	}
};
int Entity::x;
int Entity::y;

int main(){
	Entity e;
	e.x = 2;
	e.y = 3;

	Entity e1 ;
	e.x = 5;
	e1.y = 8;

	e.Print();
	e1.Print();
	std::cin.get();

}
```
## const 修改权限
fake key word  
这只是为了使代码变得更美丽的机制，  
一个承诺你不会去改变它，但是你可以打破它  
```c++
//不行
const int MAX_age=5;
MAX_age=2;
// 你不能修改指针指向的内存内容，指向常数的指针const 在*前
const int*p =new int;
int const* p =new int;
// 指针常量，指向地址不可修改const 在*后
 int*const p =new int;
// 既不能修改地址页表不可改值
const int *const p
*a=2;
a=(int*)MAX_age;

class Entity{

private:
//这只会使x变成指针
	int* m_x,m_y;
//这样
	int* m_x,*m_y;
// 使用mutable关键字会使得你的属性可以在const的方法中修改
	mutable int var;
public:
// 只和方法有关，表示方法不能修改数据成员|属性
	int GetX() const
	{
		var=2;
		return m_x;
	}
}
// 有点鸟用
void Print(const Entity &e)
{
	std::cout<<GetX()<<std::endl;
}
//如果你把const去掉，你将不能在这个函数内调用该方法，因为这个函数的参数是一个没有修改权限的const 类实例的引用
```
### new OP
找空闲分区表 连续分配并调用构造函数
你可以overwrote it
```c++
Entity *e=new Entity();
Entity *e=(*Entity)malloc(sizeof(Entity))
//这两者只有是否调用构造函数的区别

delete e;
// 如果分配的是数组的话
int* b=new int[50];

delete []b;
// new 可以显式带参数指明分配的地址空间
```
### 隐式和显式关键字inplicit&explicit
explicit 禁止了隐式类型转换
### operate and overwrote
java 和c#只支持部分op的重载，而c++支持对op的完全控制
### this point
指向类实例的一个指针
### heap和stack的object scope
```c++
//错误代码 ，无效的创建数组函数，因为该数组在函数内部就g了
int* createarray(){
	int array[50];
	return array;
// 返回的是一个内存stack 的 指针 ，可惜这片空间已经被释放了
}
```
可以创建一个作用域指针类 smart point unic point
mutex locking

### smart point
```c++
// this is the smart point 
```
#### unic point 
在heap上实现的栈作用域指针
#### share point

### <array>

```c++
#include <array>
int main()
{
	std::array<int,5>data;
	data[0]=2;
	data[4]=1;
//???
	int dataOld[5];
	dataOld=0;
	std::cin.get();
}
```
why use static array ?
array is create on the stack not the heap

### funtion point
```c++
#include<iostream>
void Helloworld()
{
	std::cout<<"Hello world"<<std::endl;
}
int main(){
	auto function = &Helloworld;
	function();
	std::cin.get();
}
```
### 指向成员函数的指针
此处指代访问非静态成员函数
```c++
class Test {
	int x;
	int y;
public:
	Test(int i, int j = 0) :x(i), y(j) {};
	int get(int i, int j) {
		return i + j;
	}
};

int main() {
 
	Test t1(2), t2(4, 6);
	int (Test::* p)(int, int );
	p = &Test::get;//注意在赋值时候需要取地址
	cout << (t1.*p)(5,10) << endl;
	Test* p1 = &t2;
	cout << (p1->*p)(7, 20) << endl;
}
```
### lambda函数
一种匿名函数

### casting
#### const_cast<>()
用于常量指针转化为变量指针
#### dynamic_cast()
基类指针转化为派生类指针，会检测是否可转化
#### static_cast()
常用
#### reinterpret_cast
强制指针转换

### while中使用赋值语句
```c++
//赋值后a的值是否为0
while(a=1){

}
```
