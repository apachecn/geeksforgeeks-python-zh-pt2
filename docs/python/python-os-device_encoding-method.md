# Python | os.device_encoding()方法

> 原文:[https://www . geesforgeks . org/python-OS-device _ encoding-method/](https://www.geeksforgeeks.org/python-os-device_encoding-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

`***os.device_encoding()***`Python 中的方法用于获取与指定文件描述符相关联的设备的编码，如果它连接到终端的话。如果指定的文件描述符没有连接到终端，此方法返回无。

**注:**此方法仅在部分口味的 UNIX 上可用。

> ***语法:*** os.device_encoding(fd)
> 
> ***参数:***
> **fd** :要查询设备编码的文件描述符。
> 
> ***返回类型:*** 如果连接到终端，该方法返回一个字符串值，表示与指定文件描述符相关的设备的编码，否则为无。

**Code:** Use of os.device_encoding() method to get the encoding of the device associated with the given file descriptor

```
# Python program to explain os.device_encoding() method  

# importing os module 
import os

# File path
path = "/home/ihritik/Desktop/file.txt"

# Open the file and get 
# the file descriptor associated
# with it using os.open() method 
fd = os.open(path, os.O_RDWR | os.O_CREAT)

# Check if file descriptor fd
# is open and connected
# to a terminal using os.isatty() method
print("Connected to a terminal:", os.isatty(fd))

# Print the encoding of
# the device associated with
# the file descriptor fd
# using os.device_encoding() method
print("Device encoding:", os.device_encoding(fd)) 

# Open a new pseudo-terminal pair
# using os.openpty() method
# It will return master and slave 
# file descriptor for 
# pty ( pseudo terminal device) and
# tty ( native terminal device) respectively
master, slave = os.openpty()

# Check if file descriptor master
# is open and connected
# to a terminal using os.isatty() method
print("Connected to a terminal:", os.isatty(master))

# Print the encoding of
# the device associated with
# the file descriptor master
# using os.device_encoding() method
print("Device encoding:", os.device_encoding(master)) 
```

**Output:**

```
Connected to a terminal: False
Device encoding: None
Connected to a terminal: True
Device encoding: UTF-8

```