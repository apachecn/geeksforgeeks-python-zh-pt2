# Python | os.writev()方法

> 原文:[https://www.geeksforgeeks.org/python-os-writev-method/](https://www.geeksforgeeks.org/python-os-writev-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的`***os.writev()***`方法用于将指定缓冲区的内容写入指定的文件描述符。这里，缓冲区是一系列可变的类似字节的对象。缓冲区按指定顺序处理。第一个缓冲区的全部内容在进入第二个缓冲区之前被写入，依此类推。

一个*文件描述符*是一个小整数值，对应于当前进程已经打开的一个文件。它用于执行各种较低级别的输入/输出操作，如读、写、发送等。

**注** : `***os.writev()***`方法只在 UNIX 平台上可用。

> ***语法:*** os.writev(fd，buffers)
> 
> ***参数:***
> **fd** :待写的文件描述符。
> **缓冲区**:包含要写入指定文件描述符的数据的类似可变字节的对象序列。
> 
> ***返回类型:*** 这个方法返回一个整数值，代表实际写入的字节数。

**Code:** Use of os.writev() method to write contents of buffers to a file

```py
# Python program to explain os.writev() method

# import os module
import os

# File path
path = "./file2.txt"

# Create a file and get the
# file descriptor associated 
# with it using os.open() method
fd = os.open(path, os.O_CREAT | os.O_WRONLY)

# Bytes-like objects 
# the data to be written in the file
buffer1 = bytearray(b"GeeksForGeeks: ")
buffer2 = bytearray(b"A computer science portal ")
buffer3 = bytearray(b"for geeks")

# write the data contained in
# bytes-like objects
# to the file descriptor fd
# using os.writev() method
numBytes = os.writev(fd, [buffer1, buffer2, buffer3])

# print the content of file
with open(path) as f:
    print(f.read())

# Print the number of bytes actually written
print("Total Number of bytes actually written:", numBytes)
```

**Output:**

```py
GeeksForGeeks: A computer science portal for geeks
Total Number of bytes actually written: 50

```