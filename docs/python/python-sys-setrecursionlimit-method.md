# Python | sys . setrecursionlimit()方法

> 原文:[https://www . geesforgeks . org/python-sys-setrecursionlimit-method/](https://www.geeksforgeeks.org/python-sys-setrecursionlimit-method/)

这个 **sys 模块**提供了对解释器使用或维护的一些变量以及与解释器强交互的函数的访问。它提供了关于 python 解释器的常量、函数和方法的信息。它可以用于操作 Python 运行时环境。

`sys.setrecursionlimit()`方法用于将 Python 解释器堆栈的最大深度设置为所需的限制。这个限制防止任何程序进入无限递归，否则无限递归会导致 C 栈溢出，导致 Python 崩溃。

**注:**最高可能限值取决于平台。这应该小心进行，因为过高的限制会导致崩溃。

> **语法:** sys.setrecursionlimit(限制)
> 
> **参数:**
> **限制:**表示 python 解释器堆栈新限制的是整型的值。
> 
> **返回值:**此方法不返回任何内容。

**示例#1 :**

```
# Python program to explain sys.setrecursionlimit() method 

# Importing sys module 
import sys 

# Using sys.getrecursionlimit() method 
# to find the current recursion limit
limit = sys.getrecursionlimit()

# Print the current limit 
print('Before changing, limit of stack =', limit) 

# New limit
Newlimit = 500

# Using sys.setrecursionlimit() method 
sys.setrecursionlimit(Newlimit) 

# Using sys.getrecursionlimit() method 
# to find the current recursion limit
limit = sys.getrecursionlimit()

# Print the current limit 
print('After changing, limit of stack =', limit) 

```

**Output:**

```
Before changing, limit of stack = 1000
After changing, limit of stack = 500

```