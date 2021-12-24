# Python | os.path.commonpath()方法

> 原文:[https://www . geesforgeks . org/python-OS-path-common path-method/](https://www.geeksforgeeks.org/python-os-path-commonpath-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。 **os.path** 模块是 Python 中 **OS 模块**的子模块，用于常用路径名操作。

Python 中的`***os.path.commonpath()***`方法用于获取路径列表中最长的公共子路径。如果指定的路径列表既包含绝对路径又包含相对路径，或者是空的，该方法将产生**值错误**。与`***os.path.commonpath()***`方法不同，返回值是有效路径。
例如，考虑以下路径列表:

```
          list of paths                     Longest common sub-path
['/home/User/Photos', /home/User/Videos']        /home/User          
['/usr/local/bin', '/usr/lib']                   /usr               

```

> ***语法:*** os.path.commonpath(列表)
> 
> ***参数:***
> **路径**:路径类对象列表。类似路径的对象是代表路径的*字符串*或*字节*对象。
> 
> ***返回类型:*** 该方法返回一个字符串值，代表指定列表中最长的公共子路径。

**代码#1:** 使用 os.path.commonpath()方法

```
# Python program to explain os.path.commonpath() method 

# importing os module 
import os

# List of Paths
paths = ['/home/User/Desktop', '/home/User/Documents', 
         '/home/User/Downloads'] 

# Get the
# longest common sub-path
# in the specified list 
prefix = os.path.commonpath(paths)

# Print the 
# longest common sub-path
# in the specified list 
print("Longest common sub-path:", prefix)

# List of Paths
paths = ['/usr/local/bin', '/usr/bin'] 

# Get the
# longest common sub-path
# in the specified list 
prefix = os.path.commonpath(paths)

# Print the 
# longest common sub-path
# in the specified list 
print("Longest common sub-path:", prefix)
```

**Output:**

```
Longest common sub-path: /home/User
Longest common sub-path: /usr

```

**代码#2:** 使用 os.path.commonpath()方法

```
# Python program to explain os.path.commonpath() method 

# importing os module 
import os

# List of Paths
paths = ['/usr/local/bin', 'usr/bin'] 

# Get the
# longest common sub-path
# in the specified list 
prefix = os.path.commonpath(paths)

# Print the 
# longest common sub-path
# in the specified list 
print("Longest common sub-path:", prefix)

# The above code will raise
# ValueError as list of paths
# contains both absolute and
# relative path
```

**Output:**

```
Traceback (most recent call last):
  File "oscommonpath.py", line 12, in 
    prefix = os.path.commonpath(paths)
  File "/usr/lib/python3.6/posixpath.py", line 505, in commonpath
    raise ValueError("Can't mix absolute and relative paths") from None
ValueError: Can't mix absolute and relative paths

```

**注意:**如果指定的列表为空，`***os.path.commonpath()***`方法也会提升**值错误**。

**参考:**T2】https://docs.python.org/3/library/os.path.html