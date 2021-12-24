# Python | os.path.sameopenfile()方法

> 原文:[https://www . geesforgeks . org/python-OS-path-same openfile-method/](https://www.geeksforgeeks.org/python-os-path-sameopenfile-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。 **os.path** 模块是 Python 中 **OS 模块**的子模块，用于公共路径名操作。
***Python 中的 os.path.sameopenfile()*** 方法用于检查给定的文件描述符是否引用了同一个文件。
文件描述符是对应于当前进程已经打开的文件的小整数值。
文件描述符表示资源，并作为句柄来执行各种低级输入/输出操作，如读、写、发送等。
**例如:**标准输入通常是值为 0 的文件描述符，标准输出通常是值为 1 的文件描述符，标准错误通常是值为 2 的文件描述符。当前进程打开的其他文件将获得值 3、4、5 等等。

> ***语法:***OS . path . same openfile(fd1，fd2)
> ***参数:***
> **fd1** :文件描述符。
> **fd2** :文件描述符。
> ***返回类型:*** 该方法返回 bool 类的布尔值。如果文件描述符 fd1 和 fd2 都引用同一个文件，则该方法返回 True，否则返回 false。

**代码:**使用 os.path.sameopenfile()方法检查给定的文件描述符是否引用了同一个文件。

## 蟒蛇 3

```py
# Python program to explain os.path.sameopenfile() method

# importing os module
import os

# Path
path = "/home / ihritik / Desktop / file1.txt"

# open the file represented by
# the above given path and get
# the file descriptor associated
# with it using os.open() method
fd1 = os.open(path, os.O_RDONLY)

# open the file represented by
# the above given path and get
# the file object corresponding
# to the opened file
# using open() method
File = open(path, mode ='r')

# Get the file descriptor
# associated with the
# file object 'File'
fd2 = File.fileno()

# check whether the file descriptor
# fd1 and fd2 refer to same
# file or not
sameFile = os.path.sameopenfile(fd1, fd2)

# Print the result
print(sameFile)

# Path
path2 = "/home / ihritik / Documents / sample.txt"

# open the file represented by
# the above given path and get
# the file descriptor associated
# with it using os.open() method
fd3 = os.open(path2, os.O_RDONLY)

# check whether the file descriptor
# fd1 and fd3 refer to same
# file or not
sameFile = os.path.sameopenfile(fd1, fd3)

# Print the result
print(sameFile)

# close file descriptors
close(fd1)
close(fd2)
close(fd3)
```

**Output:** 

```py
True
False
```

**参考:**T2https://docs.python.org/3/library/os.path.html