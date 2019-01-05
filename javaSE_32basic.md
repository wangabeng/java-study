# day1
## linux基本  
1 进入命令行 win+r 输入cmd  
2 cd.. 返回上一层目录  
3 cd\进入跟目录 最高层是c 或 D等盘  
4 cd filename 进入某一个文件夹  
5 如果当前在c盘的123文件夹 想进入d盘的234文件夹 输入 cd d:/234 回车 无效 只能进入d盘 然后再cd 234 进入  
6 dir 显示出当前文件夹的所有内容  
7 cls清除屏幕

## 搭建java开发环境
1 安装开发环境 jdk 去官网下载jdk即可 用jdk7版本 
2 jdk安装完后 会自动安装jre 就是说jdk包含了jre  
3 配置环境变量 进入环境变量-系统变量（不是用户变量）-path
编辑，找到jdk的安装目录的bin目录 再path里输入分号 安装目录
```
;d:/java/jdk/bin
```

## 关于跨平台
jdk包含了jre jre包含了JDK 不同的操作系统有不同的Jre jre带jvm即虚拟机  
终端用户不用开发 只装jre即可

# day2
## 一个比特位是0或1。 

## char必须单引号包裹 而且必须是一个字符

## 变量定义后必须赋值 否则不能使用

## 8个比特位表示计算机的一个数据-字节）（计算机的最小存储世界 1个字节byte 8个比特位bit）
## 存储的时候 系统不会为你分配一个位，最少分配一个字节。

## 数据只要是整数 默认就是int类型

## 过大的整数 后面要加L
long abc = 100L;

## 浮点数默认为double类型，如果想变成float 后面加F

## 不同数据类型的数据可以互相转化吗?
数据范围大小  
小 《  大
byte < short < int < long < float < double 
范围小的可以自动转换为范围大的  范围大不能转为范围小的  
数据类型转换有2种方式  
1 自动类型转换: 范围小的可以自动转换为范围大的    
```
package TestBianlliang;

public class Test {

  public static void main(String[] args) {
    // TODO Auto-generated method stub
    int a = 1000; // 分配了4个字节
    double d = a; // 定义double类型 分配了8个字节 把100放到8个字节的空间里 是可以放的 这就是转换的原理。相当于10L的桶 装5L的油 是可以装的
    System.out.println(d); //  1000.0 自动转换
  }

}
```
2 强制类型转化: 范围大的转换成范围小的。
```
package TestBianlliang;

public class Test {

  public static void main(String[] args) {
    double d = 1.5;
    int b = (int)d; // 没有空格
    System.out.println(b);
  }

}
```

# day3 if for循环等
## scanner类 引用数据类型。功能：接收键盘的输入。 
用法示例
```
package ben.scanner;
import java.util.Scanner;

public class Test {
  public static void main (String[] args) {
    Scanner sc = new Scanner(System.in);
    int a = sc.nextInt(); // 只能输入int类型

    System.out.println(a); 
  }
}
```
sc.next() 接收字符串数据

## random类 也是个引用类型

# day4 
## case的穿透性
```
switch(a) {
 case 1: // 如果case是1 如果没有遇到break 则一直往下穿透 直到遇到break为止， 如果一直没有遇到break 则一直穿透到底 即switch结束 再往后的时候 case已经不重要了 不再判断了只执行语句
 case 2:
  // do a
 case 3:
  // do b
}
```

# day5 方法
## 方法调用内存图 05_06
![avatar](/img/方法内存图.png)

# day06
## 2个引用类型变量内存图
![avatar](/img/内存图.png)

## arrayList
使用注意事项: 集合只能存引用数据类型 不能存基本数据类型。  
如果想存基本数据类型，必须先转成引用数据类型，然后再存储。  
![avatar](/img/arraylist存储.png)

使用方法：   
先引包 import java.util.ArrayList
定义：
ArrayList<String> abc = new ArrayList<String>();  
集合添加数据
abc.add('dddds');
abc.get(index);
abc.set(索引值, 'ddddssd');
abc.size();
abc.remove(5);
abc.clear(); 清空所有元素


# day13
## 包
java自带的包在D:\Java\jdk1.8.0_172 解压src.zip 即可看到

## 状态码
200 OK 客户端请求成功  
400 bad request 客户端有语法错误 不能被客户端所理解
401  
403  
404 请求资源不存在  

500 服务器发生不可预知的错误  
503 服务器不能处理客户端的请求 一段时间后可能恢复正常  
