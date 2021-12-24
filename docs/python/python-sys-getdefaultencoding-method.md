# Python | sys . getdefaultencoding()方法

> 原文:[https://www . geesforgeks . org/python-sys-getdefaultencoding-method/](https://www.geeksforgeeks.org/python-sys-getdefaultencoding-method/)

这个 **sys 模块**提供了对解释器使用或维护的一些变量以及与解释器强交互的函数的访问。它提供了关于 python 解释器的常量、函数和方法的信息。它可以用于操作 Python 运行时环境。

`sys.getdefaultencoding()`方法用于获取 Unicode 实现使用的当前默认字符串编码。

> **语法**sys . getdefault 编码()
> 
> **参数:**该方法不接受参数。
> 
> **返回值:**此方法返回 Unicode 实现使用的当前默认字符串编码。

**示例#1 :**

```
# Python program to explain sys.getdefaultencoding() method 

# Importing sys module 
import sys 

# Using sys.getdefaultencoding() method 
encoding = sys.getdefaultencoding() 

# Print the current string encoding used 
print(encoding) 
```

**Output:**

```
utf-8

```