# Python | os.path.exists()方法

> 原文:[https://www.geeksforgeeks.org/python-os-path-exists-method/](https://www.geeksforgeeks.org/python-os-path-exists-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。 **os.path** 模块是 python 中 **OS 模块**的子模块，用于公共路径名操作。

Python 中的`***os.path.exists()***`方法用于检查指定路径是否存在。这个方法也可以用来检查给定的路径是否引用了打开的文件描述符。

> ***语法:*** os.path.exists(路径)
> 
> ***参数:***
> **路径**:表示文件系统路径的类路径对象。类似路径的对象是代表路径的*字符串*或*字节*对象。
> 
> ***返回类型:*** 这个方法返回一个类*布尔*的布尔值。如果路径存在，该方法返回*真*，否则返回*假*。

**Code #1:** Use of os.path.exists() method

```py
# Python program to explain os.path.exists() method 

# importing os module 
import os

# Specify path
path = '/usr/local/bin/'

# Check whether the specified
# path exists or not
isExist = os.path.exists(path)
print(isExist)

# Specify path
path = '/home/User/Desktop/file.txt'

# Check whether the specified
# path exists or not
isExist = os.path.exists(path)
print(isExist)
```

**Output:**

```py
True
False

```

**注意:** `***os.path.exists()***`函数可能会返回 *False* ，如果没有被授予对请求文件执行 *os.stat()* 的权限，即使路径存在。

**参考:**T2】https://docs.python.org/3/library/os.path.html