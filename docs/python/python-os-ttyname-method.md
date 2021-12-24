# Python | OS . TT name()方法

> 原文:[https://www.geeksforgeeks.org/python-os-ttyname-method/](https://www.geeksforgeeks.org/python-os-ttyname-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

`***os.ttyname()***`Python 中的方法用于获取与指定文件描述符关联的终端设备。

文件描述符是对应于文件或其他输入/输出资源(如管道或网络套接字)的小整数值。它是资源的抽象指示符，并作为句柄来执行各种较低级别的输入/输出操作，如读、写、发送等。
**例如:**标准输入通常是值为 0 的文件描述符，标准输出通常是值为 1 的文件描述符，标准错误通常是值为 2 的文件描述符。这些文件描述符，即 0 (stdin)、1 (stdout)和 2 (stderr)是我们的程序使用的标准文件描述符。当前进程打开的其他文件将获得值 3、4、5 等等。

**注意:**此方法仅在 UNIX 平台上可用，如果指定的文件描述符不与任何终端设备相关联，则会引发异常。

> **语法** os .类型 name(fd)
> 
> ***参数:***
> **fd** :文件描述符
> 
> ***返回类型:*** 该方法返回一个字符串值，代表与指定文件描述符 fd 相关联的终端设备。

**Code #1:** Use of os.ttyname() method to get the terminal device associated with a file descriptor.

```py
# Python program to explain os.ttyname() method  

# importing os module 
import os

# Standard file descriptors
# i.e 0 (stdin), 1 (stdout), and 2 (stderr)
# are used by our program 
# Get the terminal device 
# associated with these file descriptor
print("Terminal device associated with:")
print("Standard input:", os.ttyname(0))
print("Standard output:", os.ttyname(1))
print("standard error", os.ttyname(2))

# Open a new pseudo-terminal pair
# using os.openpty() method
# It will return master and slave 
# file descriptor for 
# pty ( pseudo terminal device) and
# tty ( native terminal device) respectively
master, slave = os.openpty()

# Get the terminal device 
# associated with these file descriptor
print("Master:", os.ttyname(master))
print("Slave:", os.ttyname(slave))
```

**Output:**

```py
Terminal device associated with:
Standard input: /dev/pts/0
Standard output: /dev/pts/0
standard error /dev/pts/0
Master: /dev/ptmx
Slave: /dev/pts/1

```

**代码#2:** 如果指定的文件描述符不与任何终端设备相关联

```py
# Python program to explain os.ttyname() method  

# importing os module 
import os

# If the specified file descriptor
# is not associated with any 
# terminal device, then an exception
# will be raised. For example:

# Create a pipe using os.pipe() method
# It will return a pair of 
# file descriptors (r, w) usable for
# reading and writing, respectively.
r, w = os.pipe()

# Get the terminal device associated 
# with the file descriptor r or w
print(os.ttyname(r)) 
```

**Output:**

```py
Traceback (most recent call last):
  File "getTerminalDevice.py", line 20, in 
    print(os.ttyname(r))
OSError: [Errno 25] Inappropriate ioctl for device

```

**代码#3:** 处理上述异常的方法

```py
# Python program to explain os.ttyname() method  

# importing os module 
import os

# Create a pipe using os.pipe() method
# It will return a pair of 
# file descriptors (r, w) usable for
# reading and writing, respectively.
r, w = os.pipe()

# Method 1 
# (using exception handling technique)
# Try to get the terminal device associated 
# with the file descriptor r or w
try :
    print(os.ttyname(r)) 
except OSError as error :
    print(error)
    print("File descriptor is not associated with any terminal device")

# Method 2
# using os.isatty() method
# check first if the file descriptor w
# is associated with a tty(-like) device or not
# if it is then only get the terminal
# device associated with it
if os.isatty(w) :
    print(os.ttyname(w))
else :
    print("File descriptor is not associated with any terminal device")
```

**Output:**

```py
[Errno 25] Inappropriate ioctl for device
File descriptor is not associated with any terminal device
File descriptor is not associated with any terminal device

```