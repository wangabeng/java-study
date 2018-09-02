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
首先安装jre，可以去官方下载。注意win7 32位对应的版本。
安装jre到
```
D:\Program\Java\jre1.8.0_162
```

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
