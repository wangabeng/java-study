# 用git的时候出的问题

cd C:\Program Files\Java\jdk1.8.0_172\bin
报错
Git: bash: cd: too many arguments
原因 
路径中间有空格 需要用引号包起来
解决方法
cd 'C:\Program Files\Java\jdk1.8.0_172\bin'
