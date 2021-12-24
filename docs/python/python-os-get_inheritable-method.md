# Python | os.get_inheritable()方法

> 原文:[https://www . geesforgeks . org/python-OS-get _ inheritable-method/](https://www.geeksforgeeks.org/python-os-get_inheritable-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的`***os.get_inheritable()***`方法用于获取指定文件描述符的*可继承*标志的值。

文件描述符的可继承标志表明它是否可以被子进程继承。例如:如果父进程有一个用于特定文件的文件描述符 4，并且父进程创建了一个子进程，那么如果父进程中的文件描述符 4 的可继承标志被设置，那么子进程也将有用于该文件的文件描述符 4。

> ***语法:*** os.get_inheritable(fd)
> 
> ***参数:***
> **fd** :待检查可继承标志的文件描述符。
> 
> ***返回类型:*** 该方法返回 bool 类的布尔值，该值代表指定文件描述符的可继承标志的值。

**Code:** Use of os.get_inheritable() method to get the value of “inheritable” flag of the given file descriptor.

```
# Python program to explain os.get_inheritable() method  

# importing os module 
import os

# File path
path = "/home/ihritik/Desktop/file.txt"

# Open the file and get 
# the file descriptor associated
# with it using os.open() method 
fd = os.open(path, os.O_RDWR | os.O_CREAT)

# Get the value of
# inheritable flag of the 
# file descriptor fd using
# os.get_inheritable() method
inheritable = os.get_inheritable(fd)

# print the value of inheritable flag
print("Value of inheritable flag:", inheritable)

# Value of inheritable flag can be set / unset
# using os.set_inheritable() method
# For example:
# change inheritable flag
os.set_inheritable(fd, True)

# Print the value of inheritable flag
inheritable = os.get_inheritable(fd)
print("Value of inheritable flag:", inheritable)
```

**Output:**

```
Value of inheritable flag: False
Value of inheritable flag: True

```