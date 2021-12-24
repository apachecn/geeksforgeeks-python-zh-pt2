# Python | os.path.isabs()方法

> 原文:[https://www.geeksforgeeks.org/python-os-path-isabs-method/](https://www.geeksforgeeks.org/python-os-path-isabs-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。 **os.path** 模块是 Python 中 **OS 模块**的子模块，用于公共路径名操作。

Python 中的`***os.path.isabs()***`方法用于检查指定路径是否为绝对路径。

在 Unix 平台上，绝对路径以正斜杠(“/”)开头，在 Windows 平台上，删除任何潜在的驱动器号后，绝对路径以反斜杠(“\”)开头。

> ***语法:*** os.path.isabs(路径)
> 
> ***参数:***
> **路径**:表示文件系统路径的类路径对象。
> 类似路径的对象是表示路径的*字符串*或*字节*对象。
> 
> ***返回类型:*** 这个方法返回一个类*布尔*的布尔值。如果指定路径是绝对路径，该方法返回*真*，否则返回*假*。

**代码#1:** 使用`***os.path.isabs()***`方法(在 Unix 平台上)

```py
# Python program to explain os.path.isabs() method 

# importing os.path module 
import os.path

# Path
path = '/home/User/Documents'

# Check whether the 
# specified path is an
# absolute path or not
isabs = os.path.isabs(path)
print(isabs)

# Path
path = 'home/User/Documents/'

# Check whether the 
# specified path is an
# absolute path or not
isabs = os.path.isabs(path)
print(isabs)

# Path
path = '../User/Documents/'

# Check whether the 
# specified path is an
# absolute path or not
isabs = os.path.isabs(path)
print(isabs)
```

**Output:**

```py
True
False
False

```

**代码#2:** 使用`***os.path.isabs()***`方法(在窗口上)

```py
# Python program to explain os.path.isabs() method 

# importing os.path module 
import os.path

# Path
path = r"C:\\Users\\Documents"

# Check whether the 
# specified path is an
# absolute path or not
isabs = os.path.isabs(path)
print(isabs)

# Path
path = r"\\User\\Documents"

# Check whether the 
# specified path is an
# absolute path or not
isabs = os.path.isabs(path)
print(isabs)

# Path
path = r"User\\Documents"

# Check whether the 
# specified path is an
# absolute path or not
isabs = os.path.isabs(path)
print(isabs)
```

**Output:**

```py
True
True
False

```

**参考:**T2】https://docs.python.org/3/library/os.path.html