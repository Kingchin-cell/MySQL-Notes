# MySQL基础篇

## SQL

### DDL语句

![image-20260917181259612](images/image-20260917181259612.png)



![image-20260917181922178](images/image-20260917181922178.png)

![image-20260917193843056](images/image-20260917193843056.png)

![image-20260917202105033](images/image-20260917202105033.png)

![image-20260917202320382](images/image-20260917202320382.png)

![image-20260917202432602](images/image-20260917202432602.png)

![image-20260917202500043](images/image-20260917202500043.png)

### DML语句

![image-20260919152335776](images/image-20260919152335776.png)

![image-20260919163336716](images/image-20260919163336716.png)

![image-20260919163826139](images/image-20260919163826139.png)

### DQL语句

![image-20260918195520217](images/image-20260918195520217.png)

![image-20260918202703164](images/image-20260918202703164.png)

![image-20260918203616384](images/image-20260918203616384.png)

![image-20260918210501292](images/image-20260918210501292.png)

![image-20260918212156509](images/image-20260918212156509.png)

![image-20260919143605669](images/image-20260919143605669.png)

![image-20260919150939466](images/image-20260919150939466.png)

### DCL语句

![image-20260919165626959](images/image-20260919165626959.png)

![image-20260919170035574](images/image-20260919170035574.png)

### MySQL的数据类型



![image-20260917200117312](images/image-20260917200117312.png)

![image-20260917200139158](images/image-20260917200139158.png)

![image-20260917200203547](images/image-20260917200203547.png)

## 函数

### 字符串函数

![image-20260919172942537](images/image-20260919172942537.png)

### 数值函数	

![image-20260920190535657](images/image-20260920190535657.png)

### 日期函数

![image-20260920192534163](images/image-20260920192534163.png)

例如date_add('2000-01-01',interval 1 day) ;  --得到2000-01-02

### 流程函数

![image-20260920193201834](images/image-20260920193201834.png)

例如case when workaddress='上海'then'一线城市' when '北京'then '一线城市'else '二线城市' end;



## 约束

### 概述

![image-20260920204537808](images/image-20260920204537808.png)

### 外键约束

![image-20260922140942995](images/image-20260922140942995.png)

 

![image-20260922141600278](images/image-20260922141600278.png)

## 多表查询

### 多表关系

![image-20260922144329471](images/image-20260922144329471.png)

![image-20260922144347778](images/image-20260922144347778.png)

![image-20260922144402542](images/image-20260922144402542.png)

### 内连接

![image-20260922153013365](images/image-20260922153013365.png)

### 外连接

![image-20260922154416821](images/image-20260922154416821.png)

### 自连接

![image-20260922161818619](images/image-20260922161818619.png)

### 联合查询

![image-20260922162901050](images/image-20260922162901050.png)

### 嵌套查询

#### 标量子查询

![image-20260922165436263](images/image-20260922165436263.png)

例如：

```
select * from emp where dept_id =(select dept.id from dept where dept.name='销售部');
select * from emp where entrydate>(select entrydate from emp where name='方东白');
```

#### 列子查询

![image-20260922174801848](images/image-20260922174801848.png)

例如：

```
select * from emp where salary>all(select salary from emp where dept_id=(select id from dept where name ='财务部'));
select * from emp where salary>any (select salary from emp where dept_id=(select id from dept where name ='研发部'));
```

#### 行子查询

![image-20260922190026124](images/image-20260922190026124.png)

例如：

```
select * from emp where (salary,managerid)=(select salary,managerid from emp where name='张无忌');
```

#### 表子查询

![image-20260922194903014](images/image-20260922194903014.png)

例如：

```
select e.*,d.* from (select * from emp where entrydate>'2006-01-01') e left join dept d on e.dept_id=d.id;
```

### 事务

#### 事务操作

![image-20260923192538347](images/image-20260923192538347.png)

![image-20260923192604326](images/image-20260923192604326.png)

#### 并发事务问题

![image-20260923200911222](images/image-20260923200911222.png)	

#### 事务隔离级别

![image-20260923200547107](images/image-20260923200547107.png)

