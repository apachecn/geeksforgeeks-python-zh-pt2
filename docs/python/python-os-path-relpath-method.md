# Python | os.path.relpath()方法

> 原文:[https://www . geesforgeks . org/python-OS-path-rel path-method/](https://www.geeksforgeeks.org/python-os-path-relpath-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。 **os.path** 模块是 Python 中 **OS 模块**的子模块，用于公共路径名操作。

Python 中的`***os.path.relpath()***`方法用于从当前工作目录或给定目录中获取给定路径的相对文件路径。

**注:**此方法只计算相对路径。不会检查给定路径或目录的存在。

> ***语法:*** os.path.relpath(path，start = os.curdir)
> 
> ***参数:***
> **路径**:表示文件系统路径的类路径对象。
> **start** (可选):表示文件系统路径的类路径对象。
> 给定路径的相对路径将根据 start 指示的目录进行计算。此参数的默认值是 OS . core dir，这是操作系统用来引用当前目录的常量字符串。
> 
> 类似路径的对象是代表路径的*字符串*或*字节*对象。
> 
> ***返回类型:*** 这个方法返回一个字符串值，代表从起始目录到给定路径的相对文件路径。

**代码:**使用 os.path.relpath()方法

```py
# Python program to explain os.path.relpath() method 

# importing os module 
import os

# Path
path = "/home / User / Desktop / file.txt"

# Path of Start directory
start = "/home / User"

# Compute the relative file path
# to the given path from the 
# the given start directory.
relative_path = os.path.relpath(path, start)

# Print the relative file path
# to the given path from the 
# the given start directory.
print(relative_path)

# Path
path = "/home / User / Desktop / file.txt"

# Compute the relative file path
# to the given path from the 
# the current directory.

# if we do not specify the start
# parameter it will default to
# os.curdir i.e current directory 
relative_path = os.path.relpath(path)

# Print the relative file path
# to the given path from the 
# the given start directory.
print(relative_path)

# Path
path = "/home / User / Desktop / file.txt"

# Path of Start directory
start = "GeeksForGeeks / home"

# Compute the relative file path
# to the given path from the 
# the given start directory.
relative_path = os.path.relpath(path, start)

# Print the relative file path
# to the given path from the 
# the given start directory.
print(relative_path)

# Path
path = "/home / User / Desktop / file.txt"

# Path of Start directory
start = "/home / User / ihritik / file.txt"

# Compute the relative file path
# to the given path from the 
# the given start directory.
relative_path = os.path.relpath(path, start)

# Print the relative file path
# to the given path from the 
# the given start directory.
print(relative_path)
```

**Output:**

```py
Desktop/file.txt
../User/Desktop/file.txt
../../../User/Desktop/file.txt
../../Desktop/file.txt

```

**参考:**T2】https://docs.python.org/3/library/os.path.html