# Python | os.path.isfile()方法

> 原文:[https://www.geeksforgeeks.org/python-os-path-isfile-method/](https://www.geeksforgeeks.org/python-os-path-isfile-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。 **os.path** 模块是 Python 中 **OS 模块**的子模块，用于公共路径名操作。

Python 中的`***os.path.isfile()***`方法用于检查指定的路径是否是现有的常规文件。

> ***语法:*** os.path.isfile(路径)
> 
> ***参数:***
> **路径**:表示文件系统路径的类路径对象。类似路径的对象是代表路径的*字符串*或*字节*对象。
> 
> ***返回类型:*** 这个方法返回一个类*布尔*的布尔值。如果指定的路径是现有的常规文件，该方法返回*真*，否则返回*假*。

**代码#1:** 使用 os.path.isfile()方法

```py
# Python program to explain os.path.isfile() method 

# importing os module 
import os

# Path
path = '/home/User/Desktop/file.txt'

# Check whether the 
# specified path is 
# an existing file
isFile = os.path.isfile(path)
print(isFile)

# Path
path = '/home/User/Desktop/'

# Check whether the 
# specified path is 
# an existing file
isFile = os.path.isfile(path)
print(isFile)
```

**Output:**

```py
True
False

```

**参考:**T2】https://docs.python.org/3/library/os.path.html