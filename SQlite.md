## SQlite

### SQlite是什么？
```sh
SQLite是一个进程内的库，实现了自给自足的、无服务器的、零配置的、事务性的 SQL 数据库引擎。它是一个零配置的数据库，这意味着
与其他数据库一样，您不需要在系统中配置。就像其他数据库，SQLite 引擎不是一个独立的进程，可以按应用程序需求进行静态或动态连
接。SQLite 直接访问其存储文件。
```
## SQlite安装
### 在Windows上安装SQlite
* 请访问[SQlite下载页面](http://www.sqlite.org/download.html),从Windows区下载预编译的二进制文件。
* 您需要下载 **sqlite-shell-win32-*.zip** 和 **sqlite-dll-win32-*.zip** 压缩文件。
* 创建文件夹 C:\sqlite，并在此文件夹下解压上面两个压缩文件，将得到 sqlite3.def、sqlite3.dll 和 sqlite3.exe 文件。
* 添加 C:\sqlite 到 PATH 环境变量，最后在命令提示符下，使用 **sqlite3** 命令，将显示如下结果。
```c
C:\>sqlite3
SQLite version 3.7.15.2 2013-01-09 11:53:05
Enter ".help" for instructions
Enter SQL statements terminated with a ";"
sqlite>
```
### 在Linux上安装SQlite

目前，几乎所有版本的 Linux 操作系统都附带 SQLite。所以，只要使用下面的命令来检查您的机器上是否已经安装了 SQLite。
```sh
$sqlite3
SQLite version 3.7.15.2 2013-01-09 11:53:05
Enter ".help" for instructions
Enter SQL statements terminated with a ";"
sqlite>
```
如果没有看到上面的结果，那么就意味着没有在 Linux 机器上安装 SQLite。因此，让我们按照下面的步骤安装 SQLite：
```sh
$ 1. sudo apt-get update
$ 2. sudo apt-get install  libsqlite3-dev
检查是否安装成功： cd  /usr/include 中查看是否有sqlite3.h文件
```
## SQlite的基本命令
1.建数据库:

    sqlite3 test.db        /*注意sqlite的版本*/
  
2.查看帮助:  

    sqlite>.help           /*注意不能在点前加空格*/
  
3.文件存放位置:  

    splite>.database
  
4.退出:  

    sqlite>.quit
  
5.查看表:  

    sqlite>.tables

6.显示表的结构:  
```
sqlite>.schema
```

## sqlite3常见语句

1.创建表:

    sqlite> create table usr(id integer primary key, name text, age integer null, gender text,
    salary real not null);
  
2.删除表:

    sqlite> drop table usr；

3.插入数据：

    sqlite> insert into usr(id, name, age, salary) values(2, ‘liu’, 20, 6000);

4.删除数据:
    
    sqlite> delete from usr where id = 2 and name = ‘lisi’；//删除一条记录

    sqlite> delete from usr where id = 2 or name = ‘lisi’；// and(与）or（或）

5.修改数据：

    sqlite> update usr set gender = ‘man’，name = ‘lisi’ where id = 3;

6.查询数据：

    sqlite> select * from usr where id = 2;

7.修改表的名称:

    sqlite> alter table oldname rename to newname;

## sqlite3的C语言接口的基本使用
```sh
注意： 使用sqlite3库进行代码的编译时，必须添加 -lsqlite3参数
比如： gcc xxxx.c   -lsqlite3
```
1.打开或者创建数据库:
```sh
int sqlite3_open(char *path, sqlite3 **db);
 db:指向sqlite句柄的指针；  成功返回0；   失败返回错误码；
```
2.出错判断:
```sh
char *sqlite3_errmsg(sqlite3*);
```
3.关闭数据库:
```sh
int sqlite3_close(sqlite3 *db);
```
4.执行sql操作
```sh
int sqlite3_exec(
  sqlite3*,                                  /* 数据库句柄 */
  const char *sql,                           /* SQL语句 */
  int (*callback)(void*,int,char**,char**),  /* 回调函数 */
  void *,                                    /* 函数参数 */
  char **errmsg                              /* 错误信息指针的地址 */
);
 返回值： 成功返回0
```
5.利用回调函数查询数据库
```sh
回调执行函数：每找到一条自动执行一次函数
typedef int （*sqlite3_callback）(
			void *para, 	//传递给函数的参数
			int f_num, 		//记录中包含的字段的数目
			char **f_value, //包含每个字段值的指针数组
			char **f_name	//包含每个字段名称的指针数组
			);
f_num 是查询到的符合条件的字段数(如果只查询一个字段的值，那么该值就是1)`
f_value是查询到的符合条件的一行记录的值(如果符合条件的字段数为1，那么该值就对应一个字段，而且只
```
## 补充函数

### sprintf
功能：将拼接好的字符串放到str中，示例代码：
```sh
 char str[128];
   sprintf(str, "insert into xxx values(%d, '%s', %d)",id, name, age);  
   //将id ，name， age里的字符串拼接放到str
```
### fprintf
功能：将格式化的语句输出到指定的流，示例代码：
```sh
fprintf(stdin, "helloworld\n")  等价于 printf("helloworld\n)
```
### atoi
功能：将一个字符串转换成对应的数字
```sh
“1234” ==》 1234
```
## 参考文献
[SQlite教程](http://www.runoob.com/sqlite/sqlite-tutorial.html)
