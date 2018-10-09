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
