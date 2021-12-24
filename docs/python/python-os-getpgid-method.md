# Python | os.getpgid()方法

> 原文:[https://www.geeksforgeeks.org/python-os-getpgid-method/](https://www.geeksforgeeks.org/python-os-getpgid-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

os 模块中的所有函数在文件名和路径无效或不可访问的情况下都会引发 **OSError** ，或者其他具有正确类型但不被操作系统接受的参数。

在类似 UNIX 的操作系统中，进程组表示一个或多个进程的集合。它用于控制信号的分布，即当一个信号指向一个过程组时，该过程组的每个成员都接收该信号。使用流程组 id 唯一标识每个流程组。
Python 中的`***os.getpgid()***`方法用于获取指定进程 id 的进程的进程组 id。如果指定的进程 id 为 0，将返回当前进程的进程组 id。当前流程的流程组 id 也可以使用`***os.getpgrp()***`方法获取。

**注意:** `***os.getpgid()***`方法只在 UNIX 平台上可用。

> ***语法:*** os.getpgid(pid)
> 
> ***参数:***
> **pid** :表示要查找进程组 id 的进程的进程 id 的整数值。如果 pid 为 0，则表示当前进程。
> 
> ***返回类型:*** 该方法返回一个整数值，该整数值代表具有指定进程 id 的进程的进程组 id。

**Code:** Use of os.getpgid() method

```
# Python program to explain os.getpgid() method 

# importing os module 
import os

# Get the process group id 
# of the current process
# using os.getpgid() method
pid = os.getpid()
pgid = os.getpgid(pid)

# Print the process group id
# of the current process
print("Process group id of the current process:", pgid)

# If pid is 0, process group id
# of the current process
# will be returned 
pid = 0
pgid = os.getpgid(pid)
print("Process group id of the current process:", pgid)

# Get the process group id
# of the current process 
# using os.getpgrp() method
pgid = os.getpgrp()
print("Process group id of the current process:", pgid)

# Get the process group id
# of the parent process
pid = os.getppid()
pgid = os.getpgid(pid)
print("process group id of the parent process:", pgid)
```

**Output:**

```
Process group id of the current process: 18938
Process group id of the current process: 18938
Process group id of the current process: 18938
process group id of the parent process: 11376

```