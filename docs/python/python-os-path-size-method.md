# Python | os.path.size()方法

> 原文:[https://www.geeksforgeeks.org/python-os-path-size-method/](https://www.geeksforgeeks.org/python-os-path-size-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。 **os.path** 模块是 Python 中 **OS 模块**的子模块，用于常用路径名操作。

Python 中的`***os.path.getsize()***`方法用于检查指定路径的大小。它以*字节*返回指定路径的大小。如果文件不存在或不可访问，该方法将引发**或**。

> ***语法:*** os.path.getsize(路径)
> 
> ***参数:***
> **路径**:表示文件系统路径的类路径对象。类似路径的对象是代表路径的*字符串*或*字节*对象。
> 
> ***返回类型:*** 该方法返回一个整数值，代表指定路径的大小，单位为*字节*。

**代码#1:** 使用 os.path.getsize()方法

```py
# Python program to explain os.path.getsize() method 

# importing os module 
import os

# Path
path = '/home/User/Desktop/file.txt'

# Get the size (in bytes)
# of specified path 
size = os.path.getsize(path)

# Print the size (in bytes)
# of specified path 
print("Size (In bytes) of '%s':" %path, size)
```

**Output:**

```py
Size (In bytes) of '/home/User/Desktop/file.txt': 243

```

**代码#2:** 使用 os.path.getsize()方法时处理错误

```py
# Python program to explain os.path.getsize() method 

# importing os module 
import os

# Path
path = '/home/User/Desktop/file2.txt'

# Get the size (in bytes)
# of specified path 
try :
    size = os.path.getsize(path)

except OSError :
    print("Path '%s' does not exists or is inaccessible" %path)
    sys.exit()

# Print the size (in bytes)
# of specified path 
print("Size (In bytes) of '% s':" % path, size)
```

**Output:**

```py
Path '/home/User/Desktop/file2.txt' does not exists or is inaccessible

```

**参考:**T2】https://docs.python.org/3/library/os.path.html