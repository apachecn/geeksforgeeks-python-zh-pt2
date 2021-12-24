# Python | os.closerange()方法

> 原文:[https://www.geeksforgeeks.org/python-os-closerange-method/](https://www.geeksforgeeks.org/python-os-closerange-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

`***os.closerange()***`Python 中的方法用于关闭 fd_low(包含)到 fd_high(不包含)范围内的所有文件描述符。关闭给定范围内的任何文件描述符时发生的任何错误都将被忽略。

*文件描述符*是对应于文件或其他输入/输出资源(如管道或网络套接字)的小整数值。文件描述符是资源的抽象指示符，并作为句柄来执行各种低级输入/输出操作，如读、写、发送等。

**例如:**标准输入通常是值为 0 的文件描述符，标准输出通常是值为 1 的文件描述符，标准错误通常是值为 2 的文件描述符。
由当前进程打开的其他文件将获得值 3、4、5 等等。

> ***语法:*** os.closerange(fd_low，fd_high)
> 
> ***参数:***
> **fd_low** :要关闭的最低文件描述符。
> **fd_high** :要关闭的最高文件描述符。
> 
> ***返回类型:*** 此方法不返回值

**代码:**使用`os.closerange()`方法关闭给定范围内的文件描述符

```
# Python program to explain os.close() method 

# importing os module 
import os

# File Paths to be opened
path1 = "/home/ihritik/Desktop/file1.txt"
path2 = "/home/ihritik/Desktop/file2.txt"
path3 = "/home/ihritik/Desktop/file3.txt"
path4 = "/home/ihritik/Desktop/file4.txt"

# open the files and get
# the file descriptor associated
# with it using os.open() method
fd1 = os.open(path1, os.O_WRONLY | os.O_CREAT)
fd2 = os.open(path2, os.O_WRONLY | os.O_CREAT)
fd3 = os.open(path3, os.O_WRONLY | os.O_CREAT)
fd4 = os.open(path4, os.O_WRONLY | os.O_CREAT)

# Perform some operation
# Lets write a string
s = "GeeksForGeeks: A computer science portal for geeks"

# Convert string to bytes object
line = str.encode(s)

# Write above string to all file
os.write(fd1, line)
os.write(fd2, line)
os.write(fd3, line)
os.write(fd4, line)

# close all file descriptors
# using os.closerange() method
fd_low = min(fd1, fd2, fd3, fd4)
fd_high = max(fd1, fd2, fd3, fd4)
os.closerange(fd_low, fd_high + 1)
print("All file descriptor closed successfully")
```

**Output:**

```
All file descriptor closed successfully

```

**注意:** `***os.closerange()***`方法相当于下面的 python 代码:

```
for fd in range(fd_low, fd_high):
    try:
        os.close(fd)
    except OSError:
        pass
```

然而`***os.closerange()***`方法比上面的代码工作得更快。