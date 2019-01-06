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
创建表操作  
```
CREATE TABLE tablename (
  uid INT,
  username VARCHAR(20),
  uaddress VARCHAR(200)
)
```