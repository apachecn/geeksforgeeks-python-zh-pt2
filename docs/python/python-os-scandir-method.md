# Python | os.scandir()方法

> 原文:[https://www.geeksforgeeks.org/python-os-scandir-method/](https://www.geeksforgeeks.org/python-os-scandir-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的 ***os.scandir()*** 方法用来获取 *os 的迭代器。目录条目*对应于目录中由指定路径给出的条目的对象。

条目以任意顺序产生，特殊条目*' '*和*“..”*不包括在内。

> **语法:** os.scandir(路径= ' . ')
> ***参数:***
> **路径:**表示文件系统路径的类路径对象。这将指定要扫描的目录。如果未指定路径，则当前工作目录将用作路径。
> 类路径对象是表示路径的字符串或字节对象。
> ***返回类型:*** 这个方法返回一个 os 的迭代器。对应于给定目录中条目的目录条目对象。

**代码:使用*****OS . scandir()*****方法**

## 蟒蛇 3

```
# Python program to explain os.scandir() method

# importing os module
import os

# Directory to be scanned
path = '/home/ihritik'

# Scan the directory and get
# an iterator of os.DirEntry objects
# corresponding to entries in it
# using os.scandir() method
obj = os.scandir(path)

# List all files and directories
# in the specified path
print("Files and Directories in '% s':" % path)
for entry in obj :
    if entry.is_dir() or entry.is_file():
        print(entry.name)

# entry.is_file() will check
# if entry is a file or not and
# entry.is_dir() method will
# check if entry is a
# directory or not.

# To Close the iterator and
# free acquired resources
# use scandir.close() method
obj.close()

# scandir.close() method is called automatically
# when the iterator is exhausted
# or garbage collected, or
# when an error happens during iterating.
```

**Output:** 

```
Files and Directories in '/home':
GeeksforGeeks
Videos
Downloads
Pictures
Documents
sample.txt
Public
Desktop
Images
R
```

**参考:**T2】https://docs.python.org/3/library/os.html#os.scandir