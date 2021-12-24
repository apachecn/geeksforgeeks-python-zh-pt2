# Python | os.openpty()方法

> 原文:[https://www.geeksforgeeks.org/python-os-openpty-method/](https://www.geeksforgeeks.org/python-os-openpty-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

使用 Python 中的`***os.openpty()***`方法打开一个新的伪终端对。该方法为 pty 和 tty 分别返回一对文件描述符(*主文件*和*从文件*)。返回的文件描述符是*不可继承的*。
顾名思义，伪终端是一种具有物理终端功能而实际上不是物理终端的设备。

**注意:**此方法仅在部分口味的 UNIX 上可用。

> ***语法:*** os.openpty()
> 
> ***参数:*** 不需要参数
> 
> ***返回类型:*** 这个方法分别为 pty 和 tty 返回一对文件描述符(主、从)。

**Code:** Use of os.openpty() method

```
# Python program to explain os.openpty() method 

# importing os module 
import os

# open new pseudo-terminal pair
# using os.openpty() method
master, slave = os.openpty()

# Get the terminal device
# name associated with
# file descriptor master 
name = os.ttyname(master)
print(name)

# Get the terminal device
# name associated with
# file descriptor slave
name = os.ttyname(slave)
print(name)
```

**Output:**

```
/dev/ptmx
/dev/pts/2

```