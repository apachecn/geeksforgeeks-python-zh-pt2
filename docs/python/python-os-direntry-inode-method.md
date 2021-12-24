# Python | os。DirEntry.inode()方法

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-OS-direntry-inode 方法/

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

**操作系统模块**的`***os.scandir()***`方法产生对应于由指定路径给出的目录中的条目的`***os.DirEntry***`对象。`***os.DirEntry***`对象具有各种属性和方法，用于公开目录条目的文件路径和其他文件属性。

`***os.DirEntry***`对象上的`***inode()***`方法用于获取一个条目的索引节点号。

**注意:** `***os.DirEntry***`对象打算在迭代后被使用和丢弃，因为对象的属性和方法会缓存它们的值，并且永远不会再次重新提取这些值。如果文件的元数据已经更改，或者如果调用 ***os.scandir()*** 方法已经很长时间。我们不会得到最新的信息。

> **语法:** inode()
> 
> **参数:**不需要参数
> 
> **返回类型:**该方法返回一个代表条目 inode 编号的整数值。

**代码:使用 ***os。DirEntry.inode()*** 方法**

```
# Python program to explain os.DirEntry.inode() method 

# importing os module  
import os

# Directory to be scanned
path = os.getcwd()

# Using os.scandir() method
# scan the specified directory
# and yield os.DirEntry object
# for each file and sub-directory

print("Directory entry name and their inode number") 
with os.scandir(path) as itr:
    for entry in itr :
        # Exclude the entry name
        # starting with '.'  
        if not entry.name.startswith('.') :
            # print entry name
            # and entry's inode() number 
            print(entry.name, " :", entry.inode())
```

**输出:**

```
Directory entry name and their inode number
Public  : 786500
Desktop  : 786497
R  : 1969824
foo.txt  : 801099
graph.cpp  : 801237
tree.cpp  : 801364
Pictures  : 786503
abc.py  : 801140
file.txt  : 801366
Videos  : 786504
images  : 1969766
Downloads  : 786498
geeksforgeeks  : 2097180
Music  : 801428
Documents  : 786501

```

**参考资料:**[https://docs . python . org/3/library/OS . html # OS。direntry . inode〔T3〕](https://docs.python.org/3/library/os.html#os.DirEntry.inode)