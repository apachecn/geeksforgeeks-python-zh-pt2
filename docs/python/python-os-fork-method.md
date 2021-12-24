# Python | os.fork()方法

> 原文:[https://www.geeksforgeeks.org/python-os-fork-method/](https://www.geeksforgeeks.org/python-os-fork-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。
在无效或不可访问的文件名和路径，或其他具有正确类型但不被操作系统接受的参数的情况下，操作系统模块中的所有函数都会引发 **OSError** 。

***os.fork()*** 方法在 Python 中是用来创建子进程的。这个方法通过调用底层操作系统函数 *fork()* 来工作。此方法在子进程中返回 0，在父进程中返回子进程的进程 id。

**注意:** ***os.fork()*** 方法仅在 UNIX 平台上可用。

> ***语法:*** os.fork()
> ***参数:*** 不需要参数
> ***返回类型:*** 此方法返回一个代表子进程在父进程中的进程 id 的整数值，而在子进程中返回 0。

**代码:**使用 os.fork()方法创建子进程

## 蟒蛇 3

```
# Python program to explain os.fork() method 

# importing os module 
import os

# Create a child process
# using os.fork() method 
pid = os.fork()

# pid greater than 0 represents
# the parent process 
if pid > 0 :
    print("I am parent process:")
    print("Process ID:", os.getpid())
    print("Child's process ID:", pid)

# pid equal to 0 represents
# the created child process
else :
    print("\nI am child process:")
    print("Process ID:", os.getpid())
    print("Parent's process ID:", os.getppid())

# If any error occurred while
# using os.fork() method
# OSError will be raised
```

**Output:** 

```
I am Parent process
Process ID: 10793
Child's process ID: 10794

I am child process
Process ID: 10794
Parent's process ID: 10793
```