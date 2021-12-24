# Python | os.write()方法

> 原文:[https://www.geeksforgeeks.org/python-os-write-method/](https://www.geeksforgeeks.org/python-os-write-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的`***os.write()***`方法用于向给定的文件描述符写入字节串。

一个*文件描述符*是一个小整数值，对应于当前进程已经打开的一个文件。它用于执行各种较低级别的输入/输出操作，如读、写、发送等。

**注意** : `***os.write()***`方法用于低级操作，应该应用于`***os.open()***`或`***os.pipe()***`方法返回的文件描述符。

> ***语法:*** os.write(fd，str)
> 
> ***参数:***
> **fd** :代表目标文件的文件描述符。
> **str** :要写入文件的类似字节的对象。
> 
> ***返回类型:*** 这个方法返回一个整数值，代表实际写入的字节数。

**Code:** Use of os.write() method to write a bytestring to a given file descriptor

```
# Python program to explain os.write() method 

# importing os module 
import os

# File path 
path = "/home / ihritik / Documents / GeeksForGeeks.txt"

# Open the file and get
# the file descriptor associated
# with it using os.open() method
fd = os.open(path, os.O_RDWR)

# String to be written
s = "GeeksForGeeks: A Computer science portal for Geeks."

# Convert the string to bytes
line = str.encode(s)

# Write the bytestring to the file
# associated with the file
# descriptor fd and get the number of
# Bytes actually written
numBytes = os.write(fd, line)

print("Number of bytes written:", numBytes)

# close the file descriptor
os.close(fd)
```

**Output:**

```
Number of bytes written: 51

```