# lesson 1
## jdk 包含
1 jre  
2 一堆工具包（比如java的编译器 javac.exe java的解释执行器 java.exe）  
3 java的一堆类库 常用的一百五十多个

## 一个java文件只能有一个public的class类

## jvm java虚拟机 就是假的机器 就是虚拟了一个假的机器 java是一个跨平台的 不是在操作系统上运行的 而是在虚拟的机器上运行 ，这个虚拟的机器可以识别java程序。

# lesson 2
## 整数类型 包括
byte 1个字节 -127-128（1个字节等于8个位）
short 2个字节 
int 4个字节
long 8个字节  

byte详解1个字节 8位 第一位是符号位 0表示正 1表示负数 

二进制1这样表示
0 1 1 1 1 1 1 1
- - - - - - - -  
原则上应该是-128  +128 2的7次方
实际上 是  -2的7次方   +2的7次方-1

##java基本数据类型的转换
1 自动转换  
原则1 数据类型可以自动从低精度向高精度转（即低精度交给高精度）。但是反过来 就会报错
int a = 1.2; // 报错 高精度不可以交给低精度  cannot convert from double to int

低精度可以交给高精度 不会出错
double a = 1; // a是1.0

精度高低  
byte<short<int<long<float<double  

思考题：  
```
float a = 3.4; // 编译出错 why  3.4默认是double类型  因为：默认在java中小数是double类型 而double类型不能自动转换成float类型
float a = 3.4f； // 最佳实践 是定义float的时候 数值后面加个f
```

2 强制转换  
高精度转换成低精度  
int a = (int) 1.2; // 1 损失精度

int a = 1;
double b = 3.4;
a = a + b; // 报错a是int型 加3.4 结果会自动往高精度走 是6.4 高精度交给低精度 会报错


# lesson 3
流程控制  

# lesson 4
注意switch  
金字塔练习

# lesson5 
对象和方法

# lesson6
对象和方法

# lesson7 
## 方法声明  
只是声明方法 并没有方法体 不是定义方法 只是声明这里有个方法  
例如  
```
// public 访问修饰符 总共有四种类型
// int 返回值 如果什么都不返回 是void
// abc 函数名
// int a 参数列表
public int abc(int a) {
  // do something
}; 
```

## 构造方法
// 不能有返回值 必须为public
public Person (int age) {
  // do something
}

## 默认构造方法是
pblic Person () {}
但是一旦声明一个构造方法 默认构造方法就被覆盖了。
比如：  
声明了一个构造方法  
```
// 如果在实例化的时候 这样创建 new Person（） 不传值 就会报错 因为默认构造方法被覆盖了 如果想不报错，就必须再创建一个不传值的构造方法 public Person () {}
public Person (int age) {
  this.age = age;
}
```
