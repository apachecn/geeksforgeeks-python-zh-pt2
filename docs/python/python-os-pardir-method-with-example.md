# Python–OS . pardir()方法示例

> 原文:[https://www . geesforgeks . org/python-OS-pardir-method-with-example/](https://www.geeksforgeeks.org/python-os-pardir-method-with-example/)

在 Python 中， [**OS 模块**](https://www.geeksforgeeks.org/os-module-python-examples/) 提供了与操作系统交互的各种功能。该模块属于 Python 标准实用程序模块，因此无需手动安装。

`os.pardir`是操作系统用来引用父目录的常量字符串。该方法也可通过`os.path.pardir()`获得

**注意:**对于基于 UNIX 的 OS，`os.pardir`是“`..`”，对于 Mac OS，`::`。

> **语法:** os.pardir
> 
> **返回类型:**引用父目录的字符串。

**Example 1:**

```
# Python program to demonstrate
# os.pardir

import os

# prints .. by default
print(os.pardir)
```

**输出:**

```
..

```

**例 2:** 打印当前工作目录的父目录。

```
# Python program to demonstrate
# os.pardir

import os

# current working directory
path = os.getcwd()
print("Current Directory:", path)

# parent directory
parent = os.path.join(path, os.pardir)

# prints parent directory
print("\nParent Directory:", os.path.abspath(parent))
```

**输出:**

```
Current Directory: /home/geeks/Desktop/gfg

Parent Directory: /home/geeks/Desktop

```

**例 3:** 获取指定路径的父路径。

```
# Python program to demonstrate
# os.pardir

import os

# path
path = "your/path/for/parent/directory"
print("Path:", path)

# parent
parent = os.path.join(path, os.pardir)

# prints the relative file path 
# for the current directory (parent)
print("\nParent:", os.path.relpath(parent))
```

**输出:**

```
Path: your/path/for/parent/directory

Parent: your/path/for/parent

```