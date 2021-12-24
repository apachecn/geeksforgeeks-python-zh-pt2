# Python | os。DirEntry.is_symlink()方法

> 原文:[https://www . geesforgeks . org/python-OS-direntry-is _ symlink-method/](https://www.geeksforgeeks.org/python-os-direntry-is_symlink-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

**操作系统模块**的`***os.scandir()***`方法产生对应于由指定路径给出的目录中的条目的`***os.DirEntry***`对象。`***os.DirEntry***`对象具有各种属性和方法，用于公开目录条目的文件路径和其他文件属性。

`***os.DirEntry***`对象上的`***is_symlink()***`方法用于检查条目是否是符号链接。

**注意:** `***os.DirEntry***`对象打算在迭代后被使用和丢弃，因为对象的属性和方法会缓存它们的值，并且永远不会再次重新提取这些值。如果文件的元数据已经更改，或者如果调用 ***os.scandir()*** 方法已经很长时间。我们不会得到最新的信息。

> **语法:** os。direntry . is _ symlink()
> 
> **参数:** None
> 
> **返回值:**如果条目是符号链接(即使断开)，则该方法返回 True，否则返回 False。

**代码#1:使用`***os.DirEntry.is_symlink()***`方法**

```
# Python program to explain os.DirEntry.is_symlink() method 

# importing os module  
import os

# Directory to be scanned
# Path
path = "/home / ihritik"

# Print all symbolic links
# in the above path

# Using os.scandir() method
# scan the specified directory
# and yield os.DirEntry object
# for each file and sub-directory
obj = os.scandir(path)

print("Symbolic links in the path '% s':" % path)
for entry in obj :
    # Check if the entry
    # is a symbolic link
    # using os.DirEntry.is_symlink() method
    if entry.is_symlink() :
        # Print symbolic link
        # full path    
        print(entry.path)

```

**输出:**

```
Symbolic links in the path '/home/ihritik':
/home/ihritik/file.txt
/home/ihritik/sample.py

```

**代码:使用`***os.DirEntry.is_symlink()***`方法**

```
# Python program to explain os.DirEntry.is_symlink() method 

# importing os module  
import os

# Directory to be scanned
# Path
path = "/home / ihritik"

# Count number of
# symbolic links
# in the above path

# Using os.scandir() method
# scan the specified directory
# and yield os.DirEntry object
# for each file and sub-directory
obj = os.scandir(path)

count = 0;

for entry in obj :
    # Check if the entry
    # is a symbolic link
    # using os.DirEntry.is_symlink() method
    if entry.is_symlink() :
        count = count + 1

print("Count of symbolic links in the path '% s':" % path, count)
```

**输出:**

```
Count of symbolic links in the path '/home/ihritik': 2

```

**参考文献:**[https://docs.python.org/3/library/os.html#os.DirEntry.is_symlink](https://docs.python.org/3/library/os.html#os.DirEntry.is_symlink)