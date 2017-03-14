# notebook

## Git
### 1.什么是git？

GIT是一个分布式版本控制工具，是世界上最先进的分布式版本控制系统。

### 2.什么是版本控制？

版本控制（Revision control）是维护工程蓝图的标准作法，能追踪工程蓝图从诞生一直到定案的过程。

## 安装Git
### ubuntu Linux
1.使用下面的命令进行安装git的工具
```sh
$ sudo apt-get install git
```
### mac ox

1.下载安装xcode开发工具里的 xcode-commnadline 本身带git管理工具
2.使用brew安装工具直接安装
```sh
$ brew install git
```
## 创建Git版本库

第一步, 先要创建一个目录, 这个目录就是用来存放仓库的.
```sh
$ mkdir html
$ cd html
```
第二步, 使用git init命令, 将当前目录创建成git仓库.
```sh
$ git init
Initialized empty Git repository in /home/user/html/.git/
```
马上就把仓库创建成功了, 并提示这是一个空仓库.  
```sh
$ ls -al
.git
```
## 增加文件

1.复制已有的文件到当前目录里：
```sh
$ cp ../../git/*.c .
```
2.创建一个新的文件
```sh
$ touch hello.c
$ vim hello.c  // 输出hello world字符串的程序
```
## 查看目录状态
查看当前目录下的文件在git仓库中的状态
```sh
$ git status
```

## 跟踪文件
将当前目录下的所有文件进行跟踪
```sh
$ git add .
```
跟踪单个文件
```sh
$  git add  hello.c
```

## 配置个人用户信息
为提交增加个人用户信息
```sh
$ git config --global user.name "dongjunfeng"
$ git config --global user.email "dongjunfeng11@outlook.com"
$ git config --global core.editor vim
```
## 提交
将文件提交至git仓库，跟踪文件
```sh
$ git commit
```
出现一个新窗口，在第一行提交文档名，第三行提交保存文件内容，例如：
```sh
first commit

init commit
```
## 查看提交信息
```sh
$ git log
```
```sh
第一行表示：commit ID       //所保存文件的编号，可以用来恢复文件与切换版本信息
第二行表示：提交作者姓名和email
第三行表示：提交的时间
第四行表示：提交信息标题
第五行表示：提交信息具体内容
```
## git diff
1.查看修改前后差别
```sh
$ git diff
```
2.两个提交版本之间的比较
```sh
$ git diff commitID-1 commitID-2
```
## 删除文件
1.删除文件后,恢复文件
```sh
$ rm -rf hello.c
$ git status
$ git checkout hello.c
```
2.从版本库里删除文件。 (真正删除文件）
```sh
$ git rm hello.c (or) rm hello.c
$ git status
$ git add .
$ git commit
```
## 版本之间切换
根据commitID， 可以进行版本切换
```sh
$ git reset --hard commitID
```

## 忽略文件
忽略不需要跟踪到git版本库的文件
```sh
$ touch .gitignore
$ vim .gitignore
-----
a.out
-----
$ git add .
$ git commit
```

## github
1.注册github账号 

![注册]（http://p1.bpimg.com/1949/cb897d3700a7d519.png）
   
   1.注册邮箱，注意不要使用QQ邮箱
    
[注册邮箱]（https://login.live.com/login.srf?wa=wsignin1.0&rpsnv=13&ct=1489489965&rver=6.7.6640.0&wp=MBI_SSL&wreply=https%3a%2f%2foutlook.live.com%2fowa%2f%3fauthRedirect%3dtrue%26realm%3doutlook.com&id=292841&whr=outlook.com&CBCXT=out&fl=wld&cobrandid=90015）
    
2.创建gitc仓库

3.从github将创建的gitc仓库克隆到本地版本库
```sh
$ git clone http://github.com/username/gitc.git
```
4.将本地版本库与github仓库进行同步（将本地提交到网络服务器）
```sh
$ git push origin master
input username:
input password:
```
5.更新本地版本库，与github进行同步。（将网络服务器同步到本地）
```sh
$ git pull
```
