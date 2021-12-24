# Python | sys . getrecursionlimit()方法

> 原文:[https://www . geesforgeks . org/python-sys-getrecursionlimit-method/](https://www.geeksforgeeks.org/python-sys-getrecursionlimit-method/)

这个 **sys 模块**提供了对解释器使用或维护的一些变量以及与解释器强交互的函数的访问。它提供了关于 python 解释器的常量、函数和方法的信息。它可以用于操作 Python 运行时环境。

`sys.getrecursionlimit()`方法用于寻找解释器的当前递归极限或寻找 Python 解释器堆栈的最大深度。这个限制防止任何程序进入无限递归，否则无限递归会导致 C 栈溢出，导致 Python 崩溃。

> **语法：** sys.getrecursionlimit（）
> 
> **参数:**该方法不接受参数。
> 
> **返回值:**该方法返回 python 解释器递归极限的当前值。

**示例#1 :**

```
# Python program to explain sys.getrecursionlimit() method 

# Importing sys module 
import sys 

# Using sys.getrecursionlimit() method 
limit = sys.getrecursionlimit() 

# Print the result 
print(limit) 
```

**Output:**

```
1000

```