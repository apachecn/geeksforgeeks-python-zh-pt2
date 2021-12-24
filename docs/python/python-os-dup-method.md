# Python | os.dup()方法

> 原文:[https://www.geeksforgeeks.org/python-os-dup-method/](https://www.geeksforgeeks.org/python-os-dup-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

*文件描述符*是对应于文件或其他输入/输出资源(如管道或网络套接字)的小整数值。文件描述符是资源的抽象指示符，并作为句柄来执行各种低级输入/输出操作，如读、写、发送等。

**例如:**标准输入通常是值为 0 的文件描述符，标准输出通常是值为 1 的文件描述符，标准错误通常是值为 2 的文件描述符。
由当前进程打开的其他文件将获得值 3、4、5 等等。

***os.dup()*** 方法在 Python 中用于复制给定的文件描述符。重复的文件描述符是不可继承的，但是在 Windows 平台上，与标准流(标准输入:0，标准输出:1，标准错误:2)相关联的文件描述符可以被子进程继承。

可继承的文件描述符意味着，如果父进程有一个文件描述符 4 用于一个特定的文件，并且父进程创建了一个子进程，那么子进程也将有一个文件描述符 4 用于同一个文件。

> ***语法:*** os.dup(fd)
> ***参数:***
> **fd** :文件描述符，需要复制。
> ***返回类型:*** 该方法返回重复的文件描述符，为整数值。

**代码:**使用 os.dup()方法复制文件描述符

## 蟒蛇 3

```py
# Python3 program to explain os.dup() method

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
dup_fd = os.dup(fd)

# The duplicated file will have
# different value but it
# will correspond to the same
# file to which original file
# descriptor was referring

# Print the value of
# duplicated file descriptor
print("Duplicated file descriptor:", dup_fd)

# Get the list of all
# file Descriptors Used
# by the current Process
# (below code works on UNIX systems)
pid = os.getpid()
os.system("ls -l/proc/%s/fd" %pid)

# Close file descriptors
os.close(fd)
os.close(dup_fd)

print("File descriptor duplicated successfully")
```

**Output:** 

```py
Original file descriptor: 3
Duplicated file descriptor: 4
total 0
lrwx------ 1 ihritik ihritik 64 Jun 14 06:45 0 -> /dev/pts/0
lrwx------ 1 ihritik ihritik 64 Jun 14 06:45 1 -> /dev/pts/0
lrwx------ 1 ihritik ihritik 64 Jun 14 06:45 2 -> /dev/pts/0
l-wx------ 1 ihritik ihritik 64 Jun 14 06:45 3 -> /home/ihritik/Desktop/file.txt
l-wx------ 1 ihritik ihritik 64 Jun 14 06:45 4 -> /home/ihritik/Desktop/file.txt
File descriptor duplicated successfully
```