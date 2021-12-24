# Python | os.path.isdir()方法

> 原文:[https://www.geeksforgeeks.org/python-os-path-isdir-method/](https://www.geeksforgeeks.org/python-os-path-isdir-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。 **os.path** 模块是 Python 中 **OS 模块**的子模块，用于公共路径名操作。

Python 中的`***os.path.isdir()***`方法用于检查指定路径是否为现有目录。此方法遵循符号链接，这意味着如果指定的路径是指向目录的符号链接，则该方法将返回 True。

> ***语法:*** os.path.isdir(路径)
> 
> ***参数:***
> **路径**:表示文件系统路径的类路径对象。
> 
> ***返回类型:*** 这个方法返回一个类*布尔*的布尔值。如果指定的路径是现有目录，则该方法返回*真*，否则返回*假*。

**代码#1:** 使用`***os.path.isdir()***`方法

```
# Python program to explain os.path.isdir() method 

# importing os.path module 
import os.path

# Path
path = '/home/User/Documents/file.txt'

# Check whether the 
# specified path is an
# existing directory or not
isdir = os.path.isdir(path)
print(isdir)

# Path
path = '/home/User/Documents/'

# Check whether the 
# specified path is an
# existing directory or not
isdir = os.path.isdir(path)
print(isdir)
```

**Output:**

```
False
True

```

**代码#2:** 如果指定的路径是符号链接

```
# Python program to explain os.path.isdir() method 

# importing os.path module 
import os.path

# Create a directory
# (in current working directory)
dirname = "GeeksForGeeks"
os.mkdir(dirname)

# Create a symbolic link
# pointing to above directory
symlink_path = "/home/User/Desktop/gfg"
os.symlink(dirname, symlink_path)

path = dirname

# Now, Check whether the 
# specified path is an
# existing directory or not
isdir = os.path.isdir(path)
print(isdir)

path = symlink_path

# Check whether the 
# specified path (which is a
# symbolic link ) is an
# existing directory or not
isdir = os.path.isdir(path)
print(isdir)
```

**Output:**

```
True
True

```

**参考:**T2】https://docs.python.org/3/library/os.path.html