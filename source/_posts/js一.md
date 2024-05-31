---
title: js逆向（其一）
tags:
- js
- py
- 逆向

---

前两周一直在填鸭式的补框架快速过视频和案例，整个人非常麻木啊，于是想开个新坑也作为一项特长发展一下，数了数为数不多的会的东西，发现爬虫这里有些意思准备发掘一下，还能和专业互补。于是决定学习一下前端的逆向

<!--more-->



## python中如何运行js

那么为什么要把js放本地来运行呢？

* 首先是方便阅读代码，逆向这个东西不像开发写给人看，是给机器看的，难免就人看不太懂，生成的东西往往是原始的机器码、汇编代码或中间表示形式，可以利用python作为高级编程语言的特性进行代码重构，有助于快速理解逻辑。
* 其次py是一种广泛使用的，易上手的编程语言，第三方库丰富功能强大，可以自动化的进行一些操作便于批量分析，提高效率
* Python在逆向工程社区中有广泛的使用和丰富的资源。有许多专门针对逆向工程的Python库、框架和工具。

## py中调用js的库

* pyv8
  * v8是google的开源js引擎，pyv8是对它的python层包装可以直接调用v8执行js代码<s>年久失修</s>

* js2py
  * 纯python实现的js解析器和翻译器它更新到了19年<s>性能不高，bug不修</s>

* pyexecjs
  * 移植自Ruby
  * 执行js的引擎可自选，但一般都使用nodejs
  * 缺点是执行大型js有点慢，特殊的输入输出会报错（输入输出参数编码一下）

* PyMiniRacer
  * 包装v8
  * 新

## 安装库

### 安装py库

```python
pip install pyexecjs
```

###  安装js环境

安装NodeJs



### 检测安装是成功

```python
import execjs
execjs.get().name()
```

出现

> Node.js(V8)

就成功了

## 简单来个案例

运行一行js代码

```python
import execjs as js

js.eval("a = new Array(1,2,3)")
```

没报错就成功 	

但是肯定不会这样一行一行进行执行

接下来介绍一个新的方式执行js代码

## 解析字符串运行代码

```python
import execjs as js


jstext = '''
function hello(str){return str;}
'''
res = js.compile(jstext)
a = res.call("hello","helloword")
print(a)
```

