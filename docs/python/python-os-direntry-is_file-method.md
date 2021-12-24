# Python | os。DirEntry.is_file()方法

> 原文:[https://www . geesforgeks . org/python-OS-direntry-is _ file-method/](https://www.geeksforgeeks.org/python-os-direntry-is_file-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

**操作系统模块**的`***os.scandir()***`方法产生对应于由指定路径给出的目录中的条目的`***os.DirEntry***`对象。`***os.DirEntry***`对象具有各种属性和方法，用于公开目录条目的文件路径和其他文件属性。

`***os.DirEntry***`对象上的`***is_file()***`方法用于检查条目是否为文件。

**注意:** `***os.DirEntry***`对象打算在迭代后被使用和丢弃，因为对象的属性和方法会缓存它们的值，并且永远不会再次重新提取这些值。如果文件的元数据已经更改，或者如果调用 ***os.scandir()*** 方法已经很长时间。我们不会得到最新的信息。

> **语法:** os。DirEntry.is_file(*，follow _ symlinks = True)
> 
> **参数:**
> **follow_symlinks:** 该参数需要一个布尔值。如果条目是符号链接，并且 follow_symlinks 为 True，则该方法将在符号链接指向的路径上运行。如果条目是符号链接，并且 follow_symlinks 为 False，则该方法将对符号链接本身进行操作。如果条目不是符号链接，则 follow _ symlinks 参数被忽略。此参数的默认值为“真”。
> 
> **返回值:**如果条目是文件，该方法返回真，否则返回假。

**代码#1:** 使用`***os.DirEntry.is_file()***`方法

```
# Python program to explain os.DirEntry.is_file() method 

# importing os module  
import os

# Directory to be scanned
# Path
path = "/home / ihritik"

# Using os.scandir() method
# scan the specified directory
# and yield os.DirEntry object
# for each file and sub-directory

print("List of all files in path '% s':" % path) 
with os.scandir(path) as itr:
    for entry in itr :
        # Check if the entry
        # is a file 
        if entry.is_file() :
            # Print file name    
            print(entry.name)
```

**Output:**

```
List of all files in path '/home/ihritik':
file.txt
tree.cpp
graph.cpp
abc.txt

```

**代码#2:** 使用`***os.DirEntry.is_file()***`方法

```
# Python program to explain os.DirEntry.is_file() method 

# importing os module  
import os

# Directory to be scanned
# Path
path = "/home / ihritik"

# Print all file names
# starting with letter 'g'
# in above specified path

# Using os.scandir() method
# scan the specified directory
# and yield os.DirEntry object
# for each file and sub-directory

with os.scandir(path) as itr:
    for entry in itr :
        # Check if the entry
        # is a file 
        if entry.is_file() :
            if entry.name.startswith('g'):
                # Print file name    
                print(entry.name)
```

**Output:**

```
graph.cpp

```

**参考文献:**[https://docs.python.org/3/library/os.html#os.DirEntry.is_file](https://docs.python.org/3/library/os.html#os.DirEntry.is_file)