# C++

## 1. Sample code

```c++
// 头文件和命名空间
#include <iostream>
using namespace std;

// 全局变量
string globalVariable;

/*使用前提前定义函数*/
string test(string a){
  return a;
}

/*主函数*/
int main(void){
  // 常量定义
  const PI = 3.14;
	// 局部变量
  float localVariable = 3.14;
  string content;
  string str;
    
  cin>>content;
  res = test(content);
  cout<<"Hello World \t"<<res<<endl;
  return 0;
}
```

文件后缀为 .cpp

编译方式： g++ sample.cpp -> a.out

运行方式： ./a.out

--------------



## 2. 基本数据类型

1. int
2. float
3. double
4. bool
5. char
6. void

使用'a'时是char，“a”是string。

------------------



## 3. 基本语法

注意每一段完整的代码块必须要用 ； 结尾。



### 3.1 变量声明

​	静态语言，变量需要提前声明且同时声明**数据类型**

​	例如代码中的 `string content` 或者`int age` 等。

​	在函数或一个代码块内部声明的变量，称为局部变量。它们只能被函数内部或者代码块内部的语句使用。

​	在所有函数外部定义的变量（通常是在程序的头部），称为全局变量。全局变量的值在程序的整个生命周期内都是有效的。

​	全局变量可以被任何函数访问。

​	命名规则一般采用驼峰命名法。



### 3.2 常量声明

​	常量名必须大写, 通常写在变量之前。

1. #define CONSTANT1（也叫宏）

2. const CONSTANT2

   



### 3.3 函数声明

​	函数声明要在**调用之前**， 和python等动态语言不同。定义时要声明**返回类型**，**函数名**和**参数类型**

​	一个C++程序必须要有main函数，main() 函数是 C++ 程序的入口函数，C++ 标准规定 main() 函数的返回值类型为 int，返回值用于表示程序的退出状态，返回 0 表示程序正常退出，返回非 0，表示出现异常。函数需要有返回值类型`int main(){}` 意思是这个函数返回int类型的变量，相应的`return 0` 意味着该函数返回了int类型0。

main函数的参数只有两种情况：

1. int main(){}
2. int main(int argc,char* argv[]){}

   其他情况全部为错误。

### 3.4 运算符

​	基本和Python一样

​	注意++ 和 --为自增自减运算符，所在位置不同作用不同。

​	在变量前使用为先操作再使用变量，在变量后使用为先使用变量再进行操作。

```c++
int a = 10;
int test2(){
  cout<<a++<<endl; // 输出为10
  cout<<a<<endl; // 输出为11
	// --同理
  return 0;
}
```



### 3.5 循环

1. for loop

   - 

     ```c++
     // for 循环执行
     for( int a = 10; a < 20; a++)
     {
       cout << "a 的值：" << a << endl;
     }
     ```

     循环中止条件为a<20，如果条件不成立则执行a++，不成立则跳出循环。

2. while loop

   - ```c++
        // while 循环执行
        while( a < 20 )
        {
            cout << "a 的值：" << a << endl;
            a++;
        }
         
        return 0;
     ```

     和Python相同。

3. do... while loop

4. - ```c++
     do
        {
            cout << "a 的值：" << a << endl;
            a = a + 1;
        }while( a < 20 );
     ```

     与while loop 区别在于至少执行一次。

### 3.6 判断

```c++
   // 检查布尔条件
   if( a == 10 )
   {
       cout << "a 的值是 10" << endl;
   }
   else if( a == 20 )
   {
       cout << "a 的值是 20" << endl;
   }
   else
   {
       cout << "没有匹配的值" << endl;
   }
```

​	和Python区别在于 elif 和else if

```c++
   switch(grade)
   {
   case 'A' :
      cout << "很棒！" << endl; 
      break;
   case 'B' :
   case 'C' :
      cout << "做得好" << endl;
      break;
   case 'D' :
      cout << "您通过了" << endl;
      break;
   case 'F' :
      cout << "最好再试一下" << endl;
      break;
   default :
      cout << "无效的成绩" << endl;
   }
```

​	判断条件为不同的case， 当grade符合case中的任何一个时执行对应的功能，如果都不符合则执行default。



### 3.7 数组

​	声明时需要**数组类型**， **数组名**和**长度**。

```c++
double newArray [10];
double newArray2[5] = {1000.0, 2.0, 3.4, 7.0, 50.0};
// 也可以不声明长度
double newArray3[] = {1000.0, 2.0, 3.4, 7.0, 50.0};
```

​	访问数组的时候和Python相同。

`newArray3[0]` = 1000.0



### 3.8 指针

&pointer 类似这样的变量，或者其他带有&的东西，遇到建议原地放弃。



### 3.9 头文件

​	`#include <iostream>` 或者 `#include "iostream"`

​	头文件是C++代码中**必须**要有的内容，两种格式代表两种不同的引用路径。类似于Python的import。

​	`cin>>` -> python中的input，接受键盘输入的string

​	`cout<<` -> python中的print。

​	注意箭头的方向。



### 3.4 命名空间

​	`Using namespace std;` 

```c++
namespace first_space {
  void fn(){
    cout<<"Function 1"<<endl;
  }
}

namespace second_space {
  void fn(){
      cout<<"Function 2"<<endl;
  }
}

int main(){
  first_space::fn();   // "Function 1"
  second_space::fn();  // "Function 2"
  return 0;
}
```

​	提前声明过命名空间（using 关键字）可以省略`first_space::` 而直接调用函数。命名空间同样有作用域，全局或者局部。

---------------



## 4 面向对象

​	面向对象的基本要素： **继承，封装，多态。**



### 4.1 类

```c++
class Box{
  public:
  	double length;
  	double height;
  	double width;
};
```

​	功能，定义和Python类似。

​	被{}包围，以分号结尾



### 4.2 访问权限

​	和JAVA不同的是访问权限无法修饰类，只能修饰类的成员。

| 问权限 | public | protected | private |
| :----: | :----: | :-------: | :-----: |
| 对本类 |  可见  |   可见    |  可见   |
| 对子类 |  可见  |   可见    | 不可见  |
| 对对像 |  可见  |  不可见   | 不可见  |



### 4.3 成员函数

​	相当于Python类中定义的函数，定义的方式有两种：

```C++
// 1
class Box{
  public:
    double length;
    double height;
    double width;
  	double getVolume(void){
      return length * height * width;
    }
};

// 2
class Box{
  public:
    double length;
    double height;
    double width;
  	double getVolume(void);
};

double Box::getVolume(void){
  return length * height * width;
}

// 调用
int main(){
  Box box1;
  box1.getVolume();
  return 0;
}
```



### 4.4 构造函数

相当于Python中的`__init(self)__` ，但是函数名和类名相同，且无返回类型。

在该类每次创建新的对象时被调用。



### 4.5 析构函数

函数名为在构造函数名前加～， 无参无返回。

在对象被删除时执行。

```c++
class Box{
  public:
  	// 构造函数
  	Box(void){
      cout<<"Class Box created."<<endl;
    }
   // 析构函数
   ～Box(){
     cout<<"Object deleted"<<endl;
   }
};

int main(){
  Box box1; // Class Box created.
  return 0; // Object deleted.
}
```



### 4.6 this

相当于Python中的`self` ,和Java中的this相同。



### 4.7 静态

1. 静态变量：`static` 关键字修饰的变量。被static修饰过的成员在所有该类的对象中只有一个相同的值。

2. 静态函数： 可以被类名直接调用，相当于Python中被`@staticmehtod` 装饰的函数。

   

### 4.8 继承

```c++
// super
class Shape{
    public:
        void setWidth(int w){
            width = w;
        }
        void setHeight(int h){
            height = h;
        }
    protected:
        int width;
        int height;
};

// child
// 继承的语法：
class Rectangle: public Shape{
    public:
        int getArea(){
            return width * height;
        }
};

int main(){
    Rectangle rec;
    rec.setWidth(10);
    rec.setHeight(10);
    cout<<rec.getArea()<<endl;
    return 0;
}
```

​	C++允许多继承，即一个子类继承多个父类。Java 只能单继承。

```c++
class DongZhuo{
  // super1
};
class DingYuan{
  // super 2
};
class Lv{
  // super 3
};

class LvBu: public DongZhuo, public DingYuan, public Lv{
    // 三姓家奴
};
```



### 4.9 重载

同一个作用域中可以声明多个功能类似的同名函数，但是参数需要不同。

```C++
class Print{
    public:
        void print(int i){
            cout<<"got integer: "<<i<<endl;
        }
        void print(string s){
            cout<<"got string: "<<s<<endl;
        }
        void print(float f){
            cout<<"got float: "<<f<<endl;
        }
};

int main(){
		Print printer;
    printer.print("10");  // got string: 10
  	printer.print(10);  // got integer: 10
  	printer.print(10.0); // got float: 10.0
    return 0;
}
```



### 4.10 多态

和JAVA相同，在继承时根据对象的种类执行相应的函数。



### 4.11 抽象

C++中任何带有public 和privatede成员的类都可以作为数据抽象的实例。

1. 类的内部收到保护。
2. 方便以后的维护。



### 4.12 封装

把数据和函数绑定在一起，可以使数据和操作过程不受到外界的干扰。

比如在脚本语言中变量命名会有很大问题，封装后的代码则会好很多。









