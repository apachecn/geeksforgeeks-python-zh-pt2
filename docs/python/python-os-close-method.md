# Python | os.close()方法

> 原文:[https://www.geeksforgeeks.org/python-os-close-method/](https://www.geeksforgeeks.org/python-os-close-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

`***os.close()***`Python 中的方法用于关闭给定的文件描述符，使其不再引用任何文件或其他资源，可以重用。
一个*文件描述符*是一个小整数值，对应于一个文件或其他输入/输出资源，如管道或网络套接字。文件描述符是资源的抽象指示符，并作为句柄来执行各种低级输入/输出操作，如读、写、发送等。
**例如:**标准输入通常是值为 0 的文件描述符，标准输出通常是值为 1 的文件描述符，标准错误通常是值为 2 的文件描述符。
当前进程打开的其他文件将获得值 3、4、5 等等。

> ***语法:*** os.close(fd)
> 
> ***参数:***
> **fd** :文件描述符，即将关闭。
> 
> ***返回类型:*** 此方法不返回值

**Code:** Use of os.close() method to close a file descriptor

```py
# Python program to explain os.close() method 

# importing os module 
import os

# Path
path = "/home/ihritik/Desktop/file2.txt"

# open the file and get
# the file descriptor associated
# with it using os.open() method
fd = os.open(path, os.O_WRONLY)

# Perform some operation
# Lets write a string
s = "GeeksForGeeks: A computer science portal for geeks"

# Convert string to bytes object
line = str.encode(s)

# Write string to file referred by
# by the file descriptor
os.write(fd, line)

# close the file descriptor
os.close(fd)
print("File descriptor closed successfully")
```

**Output:**

```py
File descriptor closed successfully

```