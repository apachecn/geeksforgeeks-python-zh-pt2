# Python | os.tcgetpgrp()方法

> 原文:[https://www.geeksforgeeks.org/python-os-tcgetpgrp-method/](https://www.geeksforgeeks.org/python-os-tcgetpgrp-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

os 模块中的所有函数在文件名和路径无效或不可访问的情况下都会引发 **OSError** ，或者其他具有正确类型但不被操作系统接受的参数。

在类似 UNIX 的操作系统中，进程组表示一个或多个进程的集合。它用于控制信号的分配，即当一个信号指向一个过程组时，该过程组的每个成员都接收该信号。使用流程组 id 唯一标识每个流程组。
Python 中的`***os.tcgetpgrp()***`方法用于获取指定文件描述符给出的与终端相关联的进程组。指定的文件描述符应该是`***os.open()***`方法返回的打开文件描述符。

**注意:** `***os.tcgetpgrp()***`方法只在 UNIX 平台上可用。

> ***语法*** os.tcgetpgrp(fd)
> 
> ***参数:***
> **fd** :与终端关联的文件描述符。
> 
> ***返回类型:*** 该方法返回一个整数值，代表指定文件描述符给出的与终端相关联的进程组 id。

**Code:** Use of os.tcgetpgrp() method

```
# Python program to explain os.tcgetpgrp() method 

# importing os module 
import os

# Get the/dev/tty file
# and get the file descriptor
# associated with it 
# using os.open() method

# '/dev / tty' is a special file
# which represents the
# controlling terminal of 
# the current process
fd = os.open("/dev/tty", os.O_RDWR)

# Get the process group associated
# with the terminal given by
# the specified file descriptor
# using os.tcgetpgrp() method
pgid = os.tcgetpgrp(fd)

# Print the process group
# associated with the controlling
# terminal of the current process
print("Process group associated with controlling\n \
         terminal of the current process:", pgid)

# Close the file descriptor
os.close(fd)
```

**Output:**

```
Process group associated with controlling
terminal of the current process: 19787

```