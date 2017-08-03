1，命令hadoop fs -du -h /user/hive/warehouse的作用是什么？  
A.查看Hive中各个数据库存储使用情况  
B.显示/user/hive/warehouse中文件列表   
C.查看hive中/user/hive/warehouse下文件个数  
答案：A

2，数据仓库的建立包括：  
A.抽取（extract）  
B.转换（transform）  
C.装载（load）  
D.应用（apply）   
答案：ABC   


3，数据仓库引擎中的服务有：  
A.数据查询  
B.数据报表  
C.数据分析   
答案：ABC

4，搭建数据仓库的数据模型有：   
A.星型模型  
B.菱形模型  
C.扇叶模型  
D.雪花模型  
答案：AB

5，HIVE数据库中的数据存储在：  
A.HDFS  
B.ORACLE数据库里  
C.MYSQL数据库里  
D.电脑C盘上  
答案：A

6，HIVE通过哪些组件帮助我们执行数据库数据的查询。  
A.解释器  
B.编译器  
C.优化器  
D.生成器  
答案：ABC

7，HIVE中通过哪条语句对查询语句进行解析？  
A.explain plan for...  
B.explain...  
C.explain for...  
D.直接运行select语句    
答案：A

8，HIVE中可以通过固定的语句来查询select的执行计划，这条语句是：  
A.select * from talbe dbms_xplan.display  
B.select * from dbms_xplan.displan  
C.select * from table(dbms_xplan.display)
D.select * from this table   
答案： C

9,在HIVE的数据导入中，最常用的load命令语法：LOAD DATA [LOCAL] INPATH 'filepath' [OVERWRITE] INTO TABLE tablename [PARTITION (partcoll=vall,partcol12=val2 ...)]中，各关键字分别代表什么意思：  
A.[LOCAL]:如果写上local，表示要导入的数据是在操作系统上，如果不写local，表示要导入的数据是在HDFS上。  
B.INPATH:表示要导入数据的路径，'filepath'表示要导入数据的目录。  
C.[OVERWRITE]:表示是否要覆盖表中存在的数据。  
D.INTO TABLE tablename：导入表的名字。    
答案：ABCD
  
10，利用sqoop导入oracle的数据到HDFS中，使用的命令是：./spoop import --connect 'the address of jdbc(e.g.,jdbc:oracle:thin:@192.168.56.101:1521:oraclename)' --username --password --table tablename [--columns 'columnsname1,columnsname2,...'] -m 'num' --target-dir 'hdfsaddress'。在这条命令中，各项含义分别为：  
A.--connect 'the address of jdbc(e.g.,jdbc:oracle:thin:@192.168.56.101:1521:oraclename)'表示需要导出的oracle数据库  
B.--username --password表示oracle的账号密码  
C.--table tablename 表示要导入的表名  
D.[--columns 'columnsname1,columnsname2,...']表示可以选择导入的列    
E.-m 'num'表示导入时所使用的mapreduce的线程数  
F.--target-dir 'hdfsaddress'表示要导入到HDFS的目录  
答案：ABCDEF

11，请说明hive中 sort by ，order by ，cluster by ，distribute by各代表什么意思。 
 A.order by ：会对输入做全局排序，因此只有一个reducer(多个reducer无法保证全局有序).只有一个reducer,会导致当输入规模较大时，需要较长的计算时间。  
B.sort by ：不是全局排序，其在数据进入reducer前完成排序.  
C.distribute by ：按照指定的字段对数据进行划分输出到不同的reduce中.  
D.cluster by ：除了具有distribute by 的功能外还兼具sort by 的功能.  
答案：ABCD  

12，请简述Hive中 split、coalesce以及collect_list函数的用法：  
A.split将字符串转化为数组  
B.coalesce(T v1,T v2,...) 返回参数中的第一个非空值；如果所有值都为null,那么返回null.  
C.collect_list列出该字段所有的值,不去重 select collect_list(id) from table.  
答案：ABC  

13，简述HIVE的分组方式：  
A.row_number() 是没有重复值的排序(即使两天记录相等也是不重复的),可以利用它来实现分页.  
B.dense_rank() 是连续排序,两个第二名仍然跟着第三名.  
C.rank()       是跳跃排序的,两个第二名下来就是第四名.  
答案：ABC  

14，通过哪些关键字可以通过shell链接到hive客户端，进行数据操作：  
A.hive -e "HQL"  
B.hive beeline -e "HQL"  
C.hive  
答案：AB  

15，HIVE数据表插入数据时，insert () table ......,括号中可使用哪些关键字？（）  
A.into  
B.append  
C.overwrite  
答案：AC  

16，hive定义一个自定义函数类时，需要继承以下哪个类？  
A.functionregistry  
B.UDF  
C.mapreduce  
答案：B  

17，Hive的计算引擎是什么？  
A.spark  
B.mapreduce  
C.HDFS  
答案：B  

18，Hive建表时，数值列的字段类型选取decimal（x,y）与Float、double的区别，下列说法正确的是？  
A.decimal（x,y）是整数，Float、double是小数  
B. Float、double在进行sum等聚合运算时，会出现JAVA精度问题.  
C. decimal（x,y）是数值截取函数，Float、double是数据类型  
答案：B  

19，当发现hive脚本执行时报错信息中包含如下内容： FAILED:ClassCastExceptionorg.apache.hadoop.hive.serde2.typeinfo.PrimitiveTypeInfocannotbecasttoorg.apache.hadoop.hive.serde2.typeinfo.DecimalTypeInfo 则此脚本最可能存在的问题是什么？  
A.网络问题  
B.GROUP BY中包含详单的字段（字段重复）  
C.字符串和数值类型转换错误   
答案：B  

20，10、Hive自定义函数jar发布有哪几种方法？  
A.使用add jar ……  
B.修改配置文件hive-site.xml中hive.aux.jars.path  
C.在${HIVE_HOME}中创建目录auxlib ，将自定义函数jar包上传至该目录  
答案：ABC
