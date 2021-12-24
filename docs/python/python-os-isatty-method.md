# Python | os.isatty()方法

> 原文:[https://www.geeksforgeeks.org/python-os-isatty-method/](https://www.geeksforgeeks.org/python-os-isatty-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

`***os.isatty()***`Python 中的方法用于检查指定的文件描述符是否打开并连接到 tty(-like)设备。“tty”最初指的是“电传打字机”，tty(-like)设备是任何类似电传打字机的设备，即终端。

文件描述符是对应于文件或其他输入/输出资源(如管道或网络套接字)的小整数值。它是资源的抽象指示符，并作为句柄来执行各种较低级别的输入/输出操作，如读、写、发送等。

> ***语法:*** os.isatty(fd)
> 
> ***参数:***
> **fd** :一个文件描述符，要检查是谁的。
> 
> ***返回类型:*** 该方法返回 bool 类的布尔值。如果指定的文件描述符已打开并连接到 tty(-like)设备，则返回 True 否则，返回 False。

**Code:** Use of os.isatty() method to check if the given file descriptor is open and connected to tty(-like) device or not

```
# Python program to explain os.isatty() method  

# importing os module 
import os

# Create a pipe using os.pipe() method
# It will return a pair of 
# file descriptors (r, w) usable for
# reading and writing, respectively.
r, w = os.pipe()

# Check if file descriptor r
# is open and connected
# to a tty(-like) device
# using os.isatty() method
print("Connected to a terminal:", os.isatty(r))

# Open a new pseudo-terminal pair
# using os.openpty() method
# It will return master and slave 
# file descriptor for 
# pty ( pseudo terminal device) and
# tty ( native terminal device) respectively
master, slave = os.openpty()

# Check if file descriptor master
# is open and connected
# to a tty(-like) device 
# using os.isatty() method
print("Connected to a terminal:", os.isatty(master))

```

**Output:**

```
Connected to a terminal: False
Connected to a terminal: True

```