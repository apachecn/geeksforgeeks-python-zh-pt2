# Python | os.set_blocking()方法

> 原文:[https://www . geesforgeks . org/python-OS-set _ blocking-method/](https://www.geeksforgeeks.org/python-os-set_blocking-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的`***os.set_blocking()***`方法用于设置指定文件描述符的阻塞模式。该方法修改了*操作系统。O_NONBLOCK* 旗。设置*操作系统。O_NONBLOCK* 标志为非阻塞模式并清除*操作系统。O_NONBLOCK* 阻塞模式标志。

阻塞模式下的文件描述符意味着系统可以阻塞读、写或连接等输入/输出系统调用。
**例如**:如果我们在 *stdin* 上调用 read 系统调用，那么我们的程序就会被阻塞(内核会将进程置于*睡眠状态*)，直到 *stdin* 上要读取的数据实际可用。

**注意:** `***os.set_blocking()***`方法仅在 Unix 平台上可用。

> ***语法:*** os.set_blocking(fd，blocking)
> 
> ***参数:***
> **fd** :要设置阻塞模式的文件描述符。
> **阻塞**:布尔值。如果要将文件描述符置于阻塞模式，则为 True 如果要将文件描述符置于非阻塞模式，则为 false。
> 
> ***返回类型:*** 此方法不返回值。

**Code:** Use of `os.set_blocking()` method to set the blocking mode of a file descriptor.

```py
# Python program to explain os.set_blocking() method 

# importing os module 
import os

# File path 
path = "/home/ihritik/Documents/file.txt"

# Open the file and get
# the file descriptor associated
# with it using os.open() method
fd = os.open(path, os.O_RDWR)

# Get the current blocking mode
# of the file descriptor
# using os.get_blocking() method
print("Blocking Mode:", os.get_blocking(fd)) 

# Change the blocking mode
blocking = False
os.set_blocking(fd, blocking)
print("Blocking mode changed")

# Get the blocking mode
# of the file descriptor
# using os.get_blocking() method
print("Blocking Mode:", os.get_blocking(fd)) 

# close the file descriptor
os.close(fd)

# A False value for blocking
# mode denotes that the file
# descriptor has been put into
# Non-Blocking mode while True
# denotes that file descriptor
# is in blocking mode.
```

**Output:**

```py
Blocking Mode: True
Blocking mode changed
Blocking Mode: False

```

**参考:**T2】https://docs.python.org/3/library/os.html#os.set_blocking