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

# day06
## arrayList
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
