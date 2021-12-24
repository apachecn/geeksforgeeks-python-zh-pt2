# Python | os.path.commonprefix()方法

> 原文:[https://www . geesforgeks . org/python-OS-path-common prefix-method/](https://www.geeksforgeeks.org/python-os-path-commonprefix-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。 **os.path** 模块是 Python 中 **OS 模块**的子模块，用于常用路径名操作。

Python 中的`***os.path.commonprefix()***`方法用于获取路径列表中最长的公共路径前缀。此方法仅返回指定列表中的公共前缀值，返回值可能是也可能不是有效路径，因为它通过逐个字符比较列表来检查公共前缀。
例如，考虑以下路径列表:

```py
          list of paths                     common prefix
['/home/User/Photos', /home/User/Videos']    /home/User/         A valid path
['/usr/local/bin', '/usr/lib']               /usr/l              Not a valid path

```

> ***语法:*** os.path.commonprefix(列表)
> 
> ***参数:***
> **路径**:路径类对象列表。类似路径的对象是代表路径的*字符串*或*字节*对象。
> 
> ***返回类型:*** 该方法返回一个字符串值，代表指定列表中最长的公共路径前缀。

**代码#1:** 使用 os.path.commonprefix()方法

```py
# Python program to explain os.path.commonprefix() method 

# importing os module 
import os

# List of Paths
paths = ['/home/User/Desktop', '/home/User/Documents', 
         '/home/User/Downloads'] 

# Get the
# longest common path prefix
# in the specified list 
prefix = os.path.commonprefix(paths)

# Print the 
# longest common path prefix
# in the specified list 
print("Longest common path prefix:", prefix)

# List of Paths
paths = ['/usr/local/bin', '/usr/bin'] 

# Get the
# longest common path prefix
# in the specified list 
prefix = os.path.commonprefix(paths)

# Print the 
# longest common path prefix
# in the specified list 
print("Longest common path prefix:", prefix)
```

**Output:**

```py
Longest common path prefix: /home/User/D
Longest common path prefix: /usr/

```

**注意:**如果指定列表为空，`***os.path.commonprefix()***`方法将返回一个空字符串。

**参考:**T2】https://docs.python.org/3/library/os.path.html