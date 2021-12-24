# Python | os.path.samestat()方法

> 原文:[https://www . geesforgeks . org/python-OS-path-same stat-method/](https://www.geeksforgeeks.org/python-os-path-samestat-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。 **os.path** 模块是 Python 中 **OS 模块**的子模块，用于公共路径名操作。

Python 中的 ***方法用于检查给定的 *stat* 元组是否引用同一个文件。Stat 元组是可能已由 os.fstat()、os.lstat()或 os.stat()方法返回的对象。它表示路径的状态。***

> ***语法:*** os.path.samestat(stat1，stat2)
> ***参数:***
> **stat1** :一个 stat 元组。
> **stat 2**:stat 元组。
> ***返回类型:*** 该方法返回 bool 类的布尔值。如果两个 stat 元组引用同一个文件，则该方法返回 True，否则返回 false。

**代码:**使用 os.path.samestat()方法检查给定的 stat 元组是否引用同一个文件。

## 蟒蛇 3

```
# Python program to explain os.path.samestat() method

# importing os module
import os

# Path
path1 = "/home / ihritik / Desktop / file.txt"

# Get the status of
# the given path
# using os.stat() method
stat1 = os.stat(path1)

# Path
path1 = "/home / ihritik / Desktop / file.txt"

# open the file and get
# the file descriptor associated
# with it
fd = os.open(path1, os.O_RDONLY)

# Get the status of the
# file associated with the
# file descriptor fd
# using os.fstat() method
stat2 = os.fstat(fd)

# Check whether the
# stat1 and stat2 refer
# to the same file
sameFile = os.path.samestat(stat1, stat2)

# Print the result
print(sameFile)

os.close(fd)

# Path
path3 = "/home / ihritik / Desktop / file.txt"

# Get the status of
# the above path
# using os.lstat() method
stat3 = os.lstat(path3)

# Check whether the
# stat1 and stat3 refer
# to the same file
sameFile = os.path.samestat(stat1, stat3)

# Print the result
print(sameFile)

# Path
path4 = "/home / ihritik / Documents / file.txt"

# Get the status of
# the above path
# using os.stat() method
stat4 = os.stat(path4)

# Check whether the
# stat1 and stat4 refer
# to the same file
sameFile = os.path.samestat(stat1, stat4)

# Print the result
print(sameFile)
```

**Output:** 

```
True
True
False
```

**参考:**T2https://docs.python.org/3/library/os.path.html