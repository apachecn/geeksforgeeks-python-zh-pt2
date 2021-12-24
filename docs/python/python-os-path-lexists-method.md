# Python | os.path.lexists()方法

> 原文:[https://www . geesforgeks . org/python-OS-path-lexists-method/](https://www.geeksforgeeks.org/python-os-path-lexists-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。 **os.path** 模块是 python 中 **OS 模块**的子模块，用于公共路径名操作。

Python 中的`***os.path.lexists()***`方法用于检查给定路径是否存在。与`***[os.path.exists()](https://www.geeksforgeeks.org/python-os-path-exists-method/)***`方法不同，对于断开的符号链接，它返回*真*。

该方法在`***os.path.lstat()***`方法不可用的平台上类似于`***[os.path.exists()](https://www.geeksforgeeks.org/python-os-path-exists-method/)***`。

> ***语法:*** os.path.lexists(路径)
> 
> ***参数:***
> **路径**:表示文件系统路径的类路径对象。类似路径的对象是代表路径的*字符串*或*字节*对象。
> 
> ***返回类型:*** 这个方法返回一个类*布尔*的布尔值。如果路径存在，该方法返回*真*，否则返回*假*。对于断开的符号链接，它将返回 True。

**Code :** Use of os.path.lexists() method

```py
# Python program to explain os.path.lexists() method 

# importing os.path module 
import os.path

# Path
path = '/home/User/Desktop'

# Check whether the Given
# path exists or not
pathExists = os.path.lexists(path)
print(pathExists)

# Path
path = '/home/User/Downloads/file.txt'

# Check whether the specified
# path exists or not
pathExists = os.path.lexists(path)
print(pathExists)

# os.path.lexists() method
# will also return True if
# the given path is
# broken symbolic link
```

**Output:**

```py
True
False

```

**参考:**T2】https://docs.python.org/3/library/os.path.html