# Python | os.set_inheritable()方法

> 原文:[https://www . geesforgeks . org/python-OS-set _ inheritable-method/](https://www.geeksforgeeks.org/python-os-set_inheritable-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的`***os.set_inheritable()***`方法用于设置指定文件描述符的*可继承*标志的值。

文件描述符的可继承标志表明它是否可以被子进程继承。例如:如果父进程有一个用于特定文件的文件描述符 4，并且父进程创建了一个子进程，那么如果父进程中的文件描述符 4 的可继承标志被设置，那么子进程也将有用于该文件的文件描述符 4。

> ***语法:*** os.set_inheritable(fd，可继承)
> 
> ***参数:***
> **fd** :要设置可继承标志的文件描述符。
> **可继承**:代表可继承标志新值的整数或布尔值。
> 
> ***返回类型:*** 此方法不返回值。

**Code:** Use of os.set_inheritable() method to set the “inheritable” flag of the given file descriptor.

```py
# Python program to explain os.set_inheritable() method  

# importing os module 
import os

# File path
path = "/home/ihritik/Desktop/file.txt"

# Open the file and get 
# the file descriptor associated
# with it using os.open() method 
fd = os.open(path, os.O_RDWR | os.O_CREAT)

# Print the current value of
# inheritable flag of the 
# file descriptor fd using
# os.get_inheritable() method
print("Current value of inheritable flag:", os.get_inheritable(fd))

# Change the inheritable flag 
# of the file descriptor fd 
# using os.set_inheritable() method
inheritable = True
os.set_inheritable(fd, inheritable)
print("Inheritable flag modified")

# Print the modified value of
# inheritable flag of the 
# file descriptor using
# os.get_inheritable() method
print("Current value of inheritable flag:", os.get_inheritable(fd))
```

**Output:**

```py
Current value of inheritable flag: False
Inheritable flag modified
Current value of inheritable flag: True

```