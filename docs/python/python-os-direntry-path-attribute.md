# Python | os。DirEntry.path 属性

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-OS-direntry-path 属性/

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

**操作系统模块**的`***os.scandir()***`方法产生对应于由指定路径给出的目录中的条目的`***os.DirEntry***`对象。`***os.DirEntry***`对象具有各种属性和方法，用于公开目录条目的文件路径和其他文件属性。

`***os.DirEntry***`对象的`***path***`属性用于获取条目的完整路径名。只有在 *os.scandir()* 方法中使用的路径参数是绝对的，完整路径才是绝对的。同样，如果 *os.scandir()* 方法路径参数是文件描述符，那么`***os.DirEntry.path***`属性的值与`***os.DirEntry.name***`属性相同。

**注意:** `***os.DirEntry***`对象打算在迭代后被使用和丢弃，因为对象的属性和方法会缓存它们的值，并且永远不会再次重新提取这些值。如果文件的元数据已经更改，或者如果调用 ***os.scandir()*** 方法已经很长时间。我们不会得到最新的信息。

> **语法:** os。DirEntry.path
> 
> **参数:** None
> 
> **返回值:**如果 os.scandir() path 参数为 bytes，则该属性返回一个 bytes 值，否则返回一个代表条目完整路径的字符串值。

**代码#1:** 使用`***os.DirEntry.path***`属性

```
# Python program to explain os.DirEntry.path attribute 

# importing os module  
import os

# Directory to be scanned
# Current working directory
path = os.getcwd()

# Using os.scandir() method
# scan the specified directory
# and yield os.DirEntry object
# for each file and sub-directory

print("Full path of all directory entry in '% s':" % path) 
with os.scandir(path) as itr:
    for entry in itr :
        # Exclude the entry name
        # starting with '.'  
        if not entry.name.startswith('.') :
            # print entry's name
            # and its full path 
            print(entry.name, ":", entry.path)
```

输出:

```
Full path of all directory entry in '/home/ihritik':
Public : /home/ihritik/Public
Desktop : /home/ihritik/Deskop
R : /home/ihritik/R
foo.txt : /home/ihritik/foo.txt
graph.cpp : /home/ihritik/graph.cpp
tree.cpp : /home/ihritik/tree.cpp
Pictures : /home/ihritik/Pictures
abc.py : /home/ihritik/abc.py
file.txt : /home/ihritik/file.txt
Videos : /home/ihritik/Videos
images : /home/ihritik/images
Downloads : /home/ihritik/Downloads
GeeksforGeeks : /home/ihritik/GeeksforGeeks
Music : /home/ihritik/Music
Documents : /home/ihritik/Documents

```

**参考资料:**[https://docs . python . org/3/library/OS . html # OS。DirEntry.path](https://docs.python.org/3/library/os.html#os.DirEntry.path)