# 用git的时候出的问题
```
cd C:\Program Files\Java\jdk1.8.0_172\bin
报错
Git: bash: cd: too many arguments
原因 
路径中间有空格 需要用引号包起来
解决方法
cd 'C:\Program Files\Java\jdk1.8.0_172\bin'
```

# java的安装
1 先要有运行java的环境  
方法1.1 安装java运行环境方法一（不推荐 不能手动编译 只能通过编译软件eclipse编译） 
首先安装jre，可以去官方下载。注意win7 32位对应的版本。
安装jre到
```
D:\Program\Java\jre1.8.0_162
```  
此时在命令行 java 会输出命令提示，但是如果输入javac 则提示不是内部命令。就是说java的运行环境已经生成，只是同javac不能编译，如果安装eclipse就可以用eclipse来编译。

方法1-2
    1 安装jdk（下载jdk安装后 也就自带了jre 安装jdk后会自动安装jre，需要注意的是 安装的时候不要安装在一个文件夹里）jdk安装在D:\Program\Java\jdk1.8.0，而jre安装在 D:\Program\Java\jdk1.8.0。   
    2 配置环境变量。打开环境变量窗口，在‘系统变量’-‘新建’-变量名输入：JAVA_HOME 变量值输入 D:\Program\Java\jdk1.8.0  
    3 在‘系统变量’中找到‘path’，双击编辑，在尾部添加    ;%JAVA_HOME%\bin  
    4 然后保存。在命令行中输入javac 如果出现帮助命令，则表示安装成功。


2 安装eclipse 
直接安装在 d:/java-oxygen。安装完成后打开eclipse 会让选择工作目录。
选择D:\javaworkspace

3 成功

# 开始一个新的java项目
1 打开eclipse file-new java project然后项目名称命名 hello。然后会在工作目录生成一个hello文件夹 文件夹下有几个初始化的文件
D:\javaworkspace\hello
2 在eclipse的hello项目，找到/src目录 然后鼠标右键 new-class 然后弹出一个对话框。然后给class命名Hello，注意首字母大写。
然后勾选public void main,然后确定。此时会在src下创建一个hello文件夹，生成一个
Hello.java文件。
```
package hello;

public class Hello {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		// 输入
		System.out.println("Hello world!");
	}

}
```
技巧： alt+/ 自动命令提示.
输入
```
System.out.println("Hello world!");
```
3 运行程序 点击播放按钮 会输出"Hello world!"

# 运行javac的时候出错 Picked up _JAVA_OPTIONS: -Xmx512M
可能的原因 在安装cordova的时候增加了一个环境变量  
_JAVA_OPTIONS  = -Xmx512M
解决办法  
暂时先删除此环境变量 需要的时候再装  

# 产生随机数
用 Math.randomO 来获得一个 0.0 到 1.0 之间的随机 double 值，不包括 1.0

# java中的单引号
不要在java中 使用单引号 切记

# public static viod main 主函数是不带返回值的 
public static int main 所以类似这样的写法就是错误的

# java的一个冒泡排序
```
public class Sortvalue {
  static int[] lists = {3, 1, 5, 6};

  public static void main (String []args) {
    for (int i = 0; i < lists.length - 1; i++) {
      // 比较 是否交换位置
      for (int j = i + 1; j < lists.length; j++) {
        if (lists[i] < lists[j]) {
          int middleValue = lists[i];
          lists[i] = lists[j];
          lists[j] = middleValue;
        }
      }
    }

    for (int j = 0; j < lists.length; j++) {
      System.out.println(lists[j]);
    }
    
  }
}
```

# 比较对象的相等 比如String对象 不能用 == 判断 而用StringA.equals(StringB) true是相等 false是不等

# 参数错误抛出异常
```
if(n<0) {
	throw new IllegalArgumentException("错误是：" + n); // so so
}
```
一旦抛出异常，thorw之后的代码就不会执行了

# 数值类型的转换
总是可以将一个数值陚给支持更大数值范围类型的变量，例如，可以将 long 型的值陚给 float 型变量。但是，如果不进行类型转换，就不能将一个值賦给范围较小类型的变量。  
Java 将自动拓宽一个类型，但是，缩窄类型必须显式完成。将一个小范围类型的变量转换为大范围类型的变量称为拓宽类型（ widening a type ), 把大范围类型的变量转换为小范围类型的变量称为缩窄类型（ narrowing a type)。
比如  
```
int a = 123;
double b = a; // 123.0 可以将一个数值陚给支持更大数值范围类型的变量
// int c = b;  // 此时就无法编译 必须把发范围的类型强制转换为小范围的
int c = (int)b; // 123 强制转换后就不会报错

```
# 超出预期的整数除法
当两个操作数是整数时，/ 操作符执行一个整数除法，操作的结果是整数，小数部分被截去。要强制两个整数执行一个浮点数除法时，将其中一个整数转换为浮点数值。

# 比较两个浮点数是否相等
不能直接比较 
```
double x = 1.0 - 0.1 - 0.1 - 0.1 - 0.1 - 0.1;
System.out.println(x == 0. S); // 本来应该是true的 但是确是false
// 正确的比较方法
final double EPSILON = IE-14;
double x = 1.0 - 0.1 - 0.1 - 0.1 - 0.1 - 0.1;
if (Math.abs(x - 0. S) < EPSILON)
System.out.printlnCx + " is approximately 0.5")；// 将显示 0.S000000000000001近似等于 0.5

```

# 理解异或 a^b 等价于a!=b 只有a和b不相等 才成立
如果a为true b为true 则表达式为false ；如果a为false b为false 则表达式为false；如果a为true b为false 则表达式为true；

# Java中一元加号和二元加法有什么区别
一元运算符有且只有一个运算参数  
二元运算符有且只有两个运算参数  
例如 负号 - 1 ; 它只能运算一个数据  
加号 1+ 2 ；参加运算的只能是两个数据多或者少都出错 它是二元运算符  

# java中操作符优先级
最高到最低 递减
```
最高级 var++ 或 var--(后置操作符)
	+ - （一元加 一元减） ++var --var （前置操作符）
	(type)value (类型转换)
	! (非)
	*、/、％(乘法、除法和求余运算）
	+、- (二元加法和减法）
	<、<=、>、>= (比较操作符）
	=、!=(相等操作符）
	^ (异或）
	&&(条件与）
	|| (条件或）

最低级   =、+= 、-=、*=、/=、％=(陚值搡作符）

```

# 入坑记 java静态方法不可以调用非静态方法和成员 例如
```
package how2j;

public class Hero {
	boolean b = true;
	static double abc = 12.0;
	
	public static void main(String[] args) {
		if (b) {
			System.out.println(b);
			System.out.println(abc);
		}
	}


}
```
运行时报错： Cannot make a static reference to the non-static field b  
解决办法：boolean b = true; 改为 static boolean b = true;

# 泛型
```
//  泛型：就是一种不确定的数据类型。
// 比如：ArrayList<E> E就是泛型。 这种不确定的数据类型需要在使用这个类的时候才能够确定出来。
// 泛型可以省略，如果省略，默认泛型是Object类型。
// 泛型的好处：
//   1. 省略了强转的代码。
//   2. 可以把运行时的问题提前到编译时期。
public class Demo01Generic {
    public static void main(String[] args) {


        //创建集合不给出泛型
        ArrayList list = new ArrayList();
        list.add("hello");
        list.add("java");
        list.add("world");
        //遍历集合
        for (Object obj : list) System.out.println(obj);
//进行遍历，打印出每个字符串长度
        for (Object obj : list) {
            String str = (String) obj;/*此处练习了向下转型*/
            System.out.println(str.length());
        }
        //创建集合给出泛型
        ArrayList<String> list2 = new ArrayList<>();
        //添加元素
        list2.add("helloo");
        list2.add("helo");
        list2.add("world");
         //list2.add(100);编译的时候就会报错，如果没有给出泛型，则不会报错
        //使用增强for遍历集合
        for (String str2 : list2
                ) {
            System.out.println(str2);

        }
    }

}

```
# 引包调用类出现问题 The constructor Indivi() is not visible 
原因 构造函数未设置public属性

# 泛型demo
1 src下新建包 定义泛型工具类 abeng.test.cn 新建 Tool.java； 
```
package abeng.test.cn;

// 泛型可以理解为定义一个未知的类型
public class Tool<E> {
	public E abc;
	// 构造函数必须为public
	public Tool (E edd) {
		this.abc = edd;
	}
}
```
2 src下新建包 使用泛型类 abeng.test.com 新建UseTool.java;
```
package abeng.test.com;

import abeng.test.cn.*;

public class UseTool {
	public static void main (String[] args) {
		// Volume<Circle> c1v=new Volume<Circle>(c1,2.5) 使用泛型类
		Tool<String> a = new Tool<String>("abeng");
		System.out.println(a.abc);
	}
}
```
