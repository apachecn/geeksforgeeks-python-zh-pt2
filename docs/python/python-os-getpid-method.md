# Python | os.getpid()方法

> 原文:[https://www.geeksforgeeks.org/python-os-getpid-method/](https://www.geeksforgeeks.org/python-os-getpid-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

`***os.getpid()***`Python 中的方法用于获取当前进程的进程 ID。

> ***语法:*** os.getpid()
> 
> ***参数:*** 不需要
> 
> ***返回类型:*** 该方法返回一个表示当前进程进程标识的整数值。该方法的返回类型属于*【国际】*类。

**代码#1:** 使用 os.getpid()方法

```py
# Python program to explain os.getpid() method 

# importing os module 
import os

# Get the process ID of
# the current process
pid = os.getpid()

# Print the process ID of
# the current process
print(pid) 
```

**Output:**

```py
2699

```