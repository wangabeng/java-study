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
