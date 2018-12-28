### Welcome to use MarkDown

## 链接demo
### 内嵌式链接
- 外部连接：[百度](http://www.baidu.com)
- 内部链接1，链接仓库其他文件：[demo1](demo1.md)
- 内部链接2，链接本文档其他文件：[demo](demo2.md#代码块-demo)

### 引用试链接

- 外部链接：[百度]
- 外部链接：[百度][baidu]
- 内部链接1，链接仓库其他文件：[demo1]
- 内部链接2，链接本文档其他文件：[demo]


## 图片 demo
- 图片的MarkDown语法
	![alt](url text)
- 外部图片  
### 图片的内嵌
![baidu](https://www.baidu.com/img/xinshouye_353af22a7f305e1fb6cfa259394dea9b.png)
- 仓库内部图片 demo
![open](images/open.jpg)


### 图片的引用试链接
![baidu][baidu_image]
- 仓库内部图片 demo
![open][open_image]

## 引用 demo
> 这是一个引文。  

——出自《苦海》

多重引用
>>> 这是多重引用  


## 代码块 demo
- 行内代码
这个代码用来声明变量`b = 100`,打印变量内容 `print(b)`


- 块试代码 demo
```python
a = 100
print(a)
b = 'helloworld'
c = b[::-1]
```


    a = 100
    print(a)
    b = 'helloworld'
    c = b[::-1]


<!--- 下面是本文本用到的链接 -->

[百度]: http//www.baidu.com
[baidu]: http//www.baidu.com
[demo1]: demo1.md
[demo]: demo2.md#代码块-demo

[baidu_image]: https://www.baidu.com/img/xinshouye_353af22a7f305e1fb6cfa259394dea9b.png
[open_image]: images/open.jpg

# 学习二
# 分割线  HTML代码  表格  GFM

---

## 水平分割线 
    <hr> Horizontal Rule  
    
    hello
    
---

    <hr> Horizontal Rule  

***

    <hr> Horizontal Rule  

___
 

## HTML 代码 demo

### **<p align='center'> Hello World </p>**
### *<p align='left'> Hello World </p>*
### ***<p align='right'> Hello World </p>***


<!--
这些内容将被忽略
这一行也一样
-->


## 表格

|这  | 是|表头|
|----------|:---------:|-----------:|
|asdfasgas|asdfasfdd|asdfasdfasdf|
|row      | row      | row       |
|**哈哈**  | [百度]  | ![][baidu_logo]|



[百度]: http://www.baidu.com
[baidu_logo]: https://www.baidu.com/img/xinshouye_353af22a7f305e1fb6cfa259394dea9b.png



## GFM demo
GitHub Flvored MarkDown, GFM

task list
- [] task1
- [x] task1
- [x] task1
- [x] task1
- [x] task1 
 
 
emoji  

:bowtie:

 # 第三部分
 # MarkDown

## 标题Demo

# 标题1
## 标题2
### 标题3
#### 标题4
##### 标题5
###### 标题6

标题1：with =
===

标题2：with 1
---


## 段落
 
我喜欢GitHub 开源技术。  
    我的qq号是：22222222
    sdfsaddfas
    sdfsdf
    哈上岛咖啡
    撒的发生
    阿斯蒂芬
   
    


## 强调
我是**粗体**文字样式 。我是*斜体* 。我是***倾斜加粗***   
我是__粗体__文字样式 。我是*斜体* 。我是***倾斜加粗***   
我是~~删除线~~

我是删除线 文字样式
## 列表

### 无序列表Demo
* Name: wangding
* QQ: 2354345

- Name: hahahah  
  - Name:hehe  
  - email:fasdfdsaf  
  
- QQ :  123543535  


## 有序列表Demo

赫赫的个人信息
1. Name：赫赫  
  1.name：伟伟
2. QQ：23432536
4. email： 阿斯蒂芬
7. 阿什顿发斯蒂芬

```python

{
    data:
        {
            'mobile': '',
            'password': '',
            'non_fileds': ''
        }
}
```
 
