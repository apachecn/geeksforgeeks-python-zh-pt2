# Python | os.path.samefile()方法

> 原文:[https://www . geesforgeks . org/python-OS-path-same file-method/](https://www.geeksforgeeks.org/python-os-path-samefile-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。 **os.path** 模块是 Python 中 **OS 模块**的子模块，用于公共路径名操作。

Python 中的`***os.path.samefile()***`方法用于检查给定的两个路径名是否引用了同一个文件或目录。这是通过比较给定路径的设备号和 I 节点号来确定的。
该方法利用`***[os.stat()](https://www.geeksforgeeks.org/python-os-stat-method/)***`方法获取给定路径的设备号和 I 节点号。因此，如果某个`***[os.stat()](https://www.geeksforgeeks.org/python-os-stat-method/)***`调用在任一路径名上失败，就会引发异常。

> ***语法:*** os.path.samefile(路径 1，路径 2)
> 
> ***参数:***
> **路径 1** :表示第一个文件系统路径的类路径对象。
> **路径 2** :表示第二个文件系统路径的类路径对象。
> 
> 类似路径的对象是代表路径的*字符串*或*字节*对象。
> 
> ***返回类型:*** 该方法返回 bool 类的布尔值。如果两个路径引用同一个文件，此方法返回真，否则返回假。

**代码:**使用 os.path.samefile()方法检查给定的路径是否引用同一个文件或目录。

```
# Python program to explain os.path.samefile() method 

# importing os module 
import os

# Path
path1 = "/home / ihritik / Documents / file(original).txt"

# Create a symbolic link 
sym_link = "/home / ihritik / Desktop / file(shortcut).txt"
os.symlink(path1, sym_link)

# Check whether the given
# paths refer to the same
# file or directory or not
areSame = os.path.samefile(path1, sym_link)

# Print the result
print(areSame)

# In above example, sym_link is 
# a symbolic link which refers
# to path1, so os.path.samefile() method
# will return True as both refer 
# to same file

# First Path
path2 = "/home / ihritik / GeeksForGeeks"

# Second path
# consider the current working directory
# is "/home / ihritik"
path3 = os.path.join(os.getcwd(), "GeeksForGeeks")

# Check whether the given
# paths refer to the same
# file or directory or not
areSame = os.path.samefile(path2, path3)

# Print the result
print(areSame)
```

**Output:**

```
True
True

```

**参考:**T2】https://docs.python.org/3/library/os.path.html