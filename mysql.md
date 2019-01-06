# mysql最常用的4种数据类型
int 整型  
double 浮点型  
varchar 字符串型  
date 日期类型 格式为YYYY-MM-DD， 只有年月日，没有时分秒  

# 常见数据库操作(每个语句要有分号, 数据库操作没有确认项)
### 数据库操作
创建数据库（F5刷新视图）  
```
CREATE DATABASE mydatabase;
```  
显示所有的数据库  
```
SHOW DATABASES;
```
删除数据库  
```
DROP DATABASES databasename;
```
切换数据库  
```
USE databasename;
```

### 表操作
### 查看当前数据库的所有数据表
```
USE databasename;
SHOW TABLES;
```

#### 创建表操作  
```
CREATE TABLE tablename (
  uid INT,
  username VARCHAR(20),
  uaddress VARCHAR(200)
);
```
#### 主键约束  
主键是用于标识当前记录的字段。他的特点是非空，唯一。在开发中一般情况下主键是不具备任何含义，只是用于标识当前记录。
设置方法：uid INT PRIMRAY KEY
```
CREATE TABLE tablename (
  uid INT PRIMRAY KEY,
  username VARCHAR(20),
  uaddress VARCHAR(200)
);
```
如何实现主键自增长  
uid INT PRIMRAY KEY AUTO_INCREMENT