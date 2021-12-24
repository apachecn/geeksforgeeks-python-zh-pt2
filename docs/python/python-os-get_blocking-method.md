# Python | os.get_blocking()方法

> 原文:[https://www . geesforgeks . org/python-OS-get _ blocking-method/](https://www.geeksforgeeks.org/python-os-get_blocking-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

使用 Python 中的`***os.get_blocking()***`方法获取指定文件描述符的阻塞模式信息。

如果*操作系统。O_NONBLOCK* 标志未置位，这意味着指定的文件描述符处于阻塞模式，如果*操作系统，则为 False。o _ NOBLOCK*标志被设置，这意味着指定的文件描述符处于非阻塞模式。

阻塞模式下的文件描述符意味着系统可以阻塞读、写或连接等输入/输出系统调用。
**例如**:如果我们在 *stdin* 上调用 read 系统调用，那么我们的程序就会被阻塞(内核会将进程置于*睡眠状态*)，直到 *stdin* 上要读取的数据实际可用。

**注意:** `***os.get_blocking()***`方法仅在 Unix 平台上可用。

> ***语法:*** os.get_blocking(fd)
> 
> ***参数:***
> **fd** :需要阻塞模式信息的文件描述符。
> 
> ***返回类型:*** 这个方法返回一个布尔值类“bool”。True 表示文件描述符处于阻塞模式，而 False 表示文件描述符处于非阻塞模式。

**Code:** Use of os.get_blocking() method to get the blocking mode of a file descriptor

```
# Python program to explain os.get_blocking() method 

# importing os module 
import os

# File path 
path = "/home / ihritik / Documents / file.txt"

# Open the file and get
# the file descriptor associated
# with it using os.open() method
fd = os.open(path, os.O_RDWR)

# Get the blocking mode
# of the file descriptor
# using os.get_blocking() method
mode = os.get_blocking(fd)

if mode == True:
    print("File descriptor is in blocking mode")
else :
    print("File descriptor is in Non-blocking mode")

# Close the file descriptor
os.close(fd)
```

**Output:**

```
File descriptor is in blocking mode

```