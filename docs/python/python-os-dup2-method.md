# Python | os.dup2()方法

> 原文:[https://www.geeksforgeeks.org/python-os-dup2-method/](https://www.geeksforgeeks.org/python-os-dup2-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

*文件描述符*是对应于文件或其他输入/输出资源(如管道或网络套接字)的小整数值。文件描述符是资源的抽象指示符，并作为句柄来执行各种低级输入/输出操作，如读、写、发送等。

**例如:**标准输入通常是值为 0 的文件描述符，标准输出通常是值为 1 的文件描述符，标准错误通常是值为 2 的文件描述符。
由当前进程打开的其他文件将获得值 3、4、5 等等。

Python 中的 ***os.dup2()*** 方法用于将文件描述符 fd 复制到给定值 fd2。只有当 fd2 可用并且默认情况下复制的文件描述符可继承时，文件描述符才会复制到 fd2。

可继承的文件描述符意味着，如果父进程有一个文件描述符 4 用于一个特定的文件，并且父进程创建了一个子进程，那么子进程也将有一个文件描述符 4 用于同一个文件。

> ***语法:*** os.dup2(fd，fd2，可继承= True)
> ***参数:***
> **fd** :文件描述符，要复制。
> **fd2** :这是文件描述符的重复值。
> **可继承的**(可选):布尔值，真或假。此参数的默认值为真，这意味着重复的文件描述符可由子进程继承。要使其不可继承，请将其设置为 False。
> ***返回类型:*** 该方法返回第二个参数 fd2，即重复文件描述符。

**代码:**使用 os.dup2()方法复制文件描述符

## 蟒蛇 3

```
# Python3 program to explain os.dup2() method

# importing os module
import os

# File path
path = "/home/ihritik/Desktop/file.txt"

# open the file and get
# the file descriptor associated
# with it using os.open() method
fd = os.open(path, os.O_WRONLY)

# Print the value of
# file descriptor
print("Original file descriptor:", fd)

# Duplicate the file descriptor
# using os.dup2() method
dup_fd = 7
os.dup2(fd, dup_fd)

# The duplicate file descriptor
# will correspond to the same
# file to which original file
# descriptor was referring

# Print the value of
# duplicate file descriptor
print("Duplicated file descriptor:", dup_fd)

# Get the list of all
# file Descriptors Used
# by the current Process
# (Below code works on UNIX systems)
pid = os.getpid()
os.system("ls -l/proc/%s/fd" %pid)

# Close file descriptors
os.close(fd)
os.close(dup_fd)

print("File descriptor duplicated successfully")
```

**Output:** 

```
Original file descriptor: 3
Duplicated file descriptor: 7
total 0
lrwx------ 1 ihritik ihritik 64 Jun 14 06:45 0 -> /dev/pts/0
lrwx------ 1 ihritik ihritik 64 Jun 14 06:45 1 -> /dev/pts/0
lrwx------ 1 ihritik ihritik 64 Jun 14 06:45 2 -> /dev/pts/0
l-wx------ 1 ihritik ihritik 64 Jun 14 06:45 3 -> /home/ihritik/Desktop/file.txt
l-wx------ 1 ihritik ihritik 64 Jun 14 06:45 7 -> /home/ihritik/Desktop/file.txt
File descriptor duplicated successfully
```