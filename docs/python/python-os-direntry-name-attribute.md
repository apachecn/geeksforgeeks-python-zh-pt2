# Python | os。DirEntry.name attribute

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-OS-direntry-name 属性/

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

**操作系统模块**的`***os.scandir()***`方法产生对应于由指定路径给出的目录中的条目的`***os.DirEntry***`对象。`***os.DirEntry***`对象具有各种属性和方法，用于公开目录条目的文件路径和其他文件属性。

`***os.DirEntry***`对象上的`***name***`属性用于获取条目的基本文件名，相对于`***os.scandir()***`方法中使用的路径参数。

**注意:** `***os.DirEntry***`对象打算在迭代后被使用和丢弃，因为对象的属性和方法会缓存它们的值，并且永远不会再次重新提取这些值。如果文件的元数据已经更改，或者如果调用 ***os.scandir()*** 方法已经很长时间。我们不会得到最新的信息。

> **语法:** os。DirEntry.name
> 
> **参数:**无
> 
> **返回值:**该属性返回一个代表条目基本文件名的字符串值。

**代码#1:** 使用`***os.DirEntry.name***`属性

```
# Python program to explain os.DirEntry.name attribute 

# importing os module  
import os

# Directory to be scanned
# Current working directory
path = os.getcwd()

# Using os.scandir() method
# scan the specified directory
# and yield os.DirEntry object
# for each file and sub-directory

print("Base filename of all directory entry in '% s':" % path) 
with os.scandir(path) as itr:
    for entry in itr :
        # Exclude the entry name
        # starting with '.'  
        if not entry.name.startswith('.') :
            # print entry's name 
            print(entry.name)
```

输出:

```
Base filename of all directory entry in '/home/ihritik':
Public 
Desktop
R
foo.txt
graph.cpp
tree.cpp
Pictures
abc.py
file.txt
Videos
images
Downloads 
GeeksforGeeks
Music  
Documents

```

**代码#2:** 使用`***os.DirEntry.name()***`属性

```
# Python program to explain os.DirEntry.name attribute 

# importing os module  
import os

# Directory to be scanned
# Current working directory
path = os.getcwd()

# Using os.scandir() method
# scan the specified directory
# and yield os.DirEntry object
# for each file and sub-directory

print("All files and directory whose name starts with letter 'D' in '% s'" % path) 
with os.scandir(path) as itr:
    for entry in itr :
        # Check if directory entry name
        # starts with letter 'D'
        if entry.name.startswith('D') :
            # print entry's name 
            print(entry.name)
```

输出:

```
All files and directory whose name starts with letter 'D' in '/home/ihritik':
Desktop
Documents
Downloads

```

**参考资料:**[https://docs . python . org/3/library/OS . html # OS。DirEntry.name](https://docs.python.org/3/library/os.html#os.DirEntry.name)