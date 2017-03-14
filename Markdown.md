# notebook
## Markdown

Markdown 是一种轻量级标记语言，创始人为約翰·格魯伯（John Gruber）。使用易读易写的纯文本格式编写文档，然后转换成有效的XHTML(或者HTML)文档。

## 标题
使用 **#** ，可表示1-6级标题
```sh
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
```
效果：
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题

## 文字修饰符

看一下粗体字，斜体字的标记.
```sh
*这个是斜体*
_这个是斜体_

**这个是粗体**
__这个是粗体__

~~将该语句划掉~~
_斜体中 **粗体** 这么表示_
```
效果：

*这个是斜体*

_这个是斜体_

**这个是粗体**

__这个是粗体__

~~将该语句划掉~~

_斜体中 **粗体** 这么表示_

## 列表
### 无序列表

主要使用 - 和 * 来标记无序列表  （- 和 * 的作用是一样的）
```sh
- George Washington
- John Adams
* Thomas Jefferson
```
效果：
- George Washington
- John Adams
* Thomas Jefferson

## 有序列表
```sh
1. James Madison
2. James Monroe
3. John Quincy Adams
```
效果：

1. James Madison
2. James Monroe
3. John Quincy Adams

(自动排序）
```sh    
1. James Madison
1. James Monroe
1. John Quincy Adams
```
效果：
1. James Madison
1. James Monroe
1. John Quincy Adams
(递进排序）
```sh
1. Make my changes
  1. Fix bug
  2. Improve formatting
    * Make the headings bigger
2. Push my commits to GitHub
3. Open a pull request
  * Describe my changes
  * Mention all the members of my team
    * Ask for feedback
```
效果：
1. Make my changes    
  1. Fix bug    
  2. Improve formatting    
    * Make the headings bigger    
2. Push my commits to GitHub    
3. Open a pull request    
  * Describe my changes    
  * Mention all the members of my team    
    * Ask for feedback    
      
## 任务列表
```sh
- [x] Finish my changes
- [ ] Push my commits to GitHub
- [ ] Open a pull request
```
效果：

- [x] Finish my changes
- [ ] Push my commits to GitHub
- [ ] Open a pull request

## 段落

段落的前后要有空行，所谓的空行是指没有文字内容。若想在段内强制换行的方式是使用**两个以上**空格加上回车（引用中换行省略回车）。

## 区块引用

在段落的每行或者只在第一行使用符号>,还可使用多个嵌套引用，如：

```sh
> 区块引用
>> 嵌套引用 
```

效果：

> 区块引用
>> 嵌套引用 

## 链接
```sh
[github](http://github.com)
```
效果：

[github](http://github.com)

## 图片
```sh
![图片名](https://octodex.github.com/images/yaktocat.png)
```
效果：
![图片名](https://octodex.github.com/images/yaktocat.png)

## 代码块

\```c  

#include <stdio.h>  
int main(void)  
{  
printf(“hello world!”);  
return 0;  
}  
\```  


效果：
```c   
#include <stdio.h>
int main(void)
{
printf(“hello world!”);
return 0;
}
```

## 支持Emoji表情
两个冒号之间加上表情的英文表示，例如：
```sh
:smile:
```
效果：
:smile:

## 表格

```sh
学号 | 姓名 | 性别
----|------|-----
01  | 姚建  | 男
02  | 董俊峰 | 男
```
效果：

学号 | 姓名 | 性别
----|------|-----
01  | 姚建  | 男
02  | 董俊峰 | 男

