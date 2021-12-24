# Python | os.getppid()方法

> 原文:[https://www.geeksforgeeks.org/python-os-getppid-method/](https://www.geeksforgeeks.org/python-os-getppid-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

使用 Python 中的`***os.getppid()***`方法获取当前进程的父进程 ID。

> ***语法:***OS . get PID()
> 
> ***参数:*** 不需要
> 
> ***返回类型:*** 该方法返回一个整数值，表示当前进程的父进程标识。该方法的返回类型属于*【国际】*类。

**代码#1:** 使用 os.getppid()方法

```py
# Python program to explain os.getppid() method 

# importing os module 
import os

# Get the Parent process ID 
# of the current process
ppid = os.getppid()

# Print the Parent process ID 
# of the current process
print("Parent Process ID of current process:", ppid)
```

**Output:**

```py
Parent process ID of current process: 7653

```

**代码#2:** 使用 os.getppid()方法

```py
# Python program to explain os.getppid() method 

# importing os module 
import os

# Check the process ID 
# of the current process
pid = os.getpid()
print("Process ID of Current process:", pid)

# Create a child process
try:
    pid = os.fork()
except OSError:
    exit("Could not create a child process")

# In the child process 
# Check its Parent process ID
# os.getppid() will return 
# the process ID of its parent process
if pid == 0:
     parent = os.getppid()
     print("Parent process ID of child process:", parent)
```

**Output:**

```py
Process ID of Current process: 7653
Parent process ID of child process: 7653

```