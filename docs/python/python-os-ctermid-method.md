# Python | os.ctermid()方法

> 原文:[https://www.geeksforgeeks.org/python-os-ctermid-method/](https://www.geeksforgeeks.org/python-os-ctermid-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

`***os.ctermid()***`Python 中的方法用于获取进程控制终端对应的文件名。

> ***语法:*** os.ctermid()
> 
> ***参数:*** 不需要
> 
> ***返回类型:*** 该方法返回一个字符串值，表示进程控制终端对应的文件名。

**代码:**使用 os.ctermid()方法

```py
# Python program to explain os.ctermid() method 

# importing os module 
import os

# Get the filename corresponding 
# to the controlling terminal
# of the process.
filename = os.ctermid()

# Print the filename corresponding 
# to the controlling terminal
# of the process.
print(filename)
```

**Output:**

```py
/dev/tty

```