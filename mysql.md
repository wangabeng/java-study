# mysql最常用的4种数据类型
int 整型  
double 浮点型  
varchar 字符串型  
date 日期类型 格式为YYYY-MM-DD， 只有年月日，没有时分秒  

# 常见数据库操作(每个语句要有分号, 数据库操作没有确认项)
### 1 数据库操作
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

### 2 表操作
### 查看当前数据库的所有数据表
```
USE databasename;
SHOW TABLES;
```

#### 查看特定数据表
```
DESC tablename;
```

#### 删除数据表
```
DROP TABLE tablename;
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

如何实现主键自增长 非空    
uid INT PRIMRAY KEY AUTO_INCREMENT NOT NULL

### 3 改表结构操作 
#### 添加一个字段
```
ALTER TABLE tablename表名 ADD 列名字段名 数据类型 约束; 
```   

#### 修改一个字段数据类型(可以修改数据类型)
```
ALTER TABLE tablename表名 MODIFY 列名字段名 数据类型 约束; 
```   

#### 修改一个字段数据列名
```
ALTER TABLE tablename表名 CHANGE 旧列名字段名 新列名字段名 数据类型 约束; 
``` 

#### 删除一个字段数据列名
```
ALTER TABLE tablename表名 DROP 列名字段名; 
``` 

#### 修改表名
```
RENAME TABLE tablename表名 新表名; 
``` 

#### 修改表字符集
```
ALTER TABLE tablename表名 CHARACTER SET UFT-8; 
``` 

### 4 向数据表中添加数据(如果主键设置了自动增加，可以不用在插入数据时加上主键的列)  
```
INSERT INTO 表名 (列名1,列名2,列名3) VALUES (值1,值2,值3);
```

如果插入的数据包含所有的列，则可以不用给出列名
```
INSERT INTO 表名 VALUES (值1,值2,值3);
```

批量插入多条数据  
```
INSERT INTO 表名 (列名1,列名2,列名3) VALUES (值1,值2,值3),(值1,值2,值3),(值1,值2,值3);
```

### 5 对数据进行更新操作 在原有基础上修改数据  
AND 
OR  
NOT  
id IN (1,2,3,4)    
id NOT IN (1,2,3,4)    
```
UPDATE 表名 set 列1=值1, 列2=值2 WHERE id=2 AND price=20;
```

### 6 删除表中的数据(不清空AUTO_INCREMENT记录)   
```
DELETE FROM tablename WHERE id=2;
```

### 7 删除表 重新建表(AUTO_INCREMENT重置为0)  
```
TRUNCATE tablename;
```

# 查询语句
day28_25