# Python | os.getcwdb()方法

> 原文:[https://www.geeksforgeeks.org/python-os-getcwdb-method/](https://www.geeksforgeeks.org/python-os-getcwdb-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

os 模块中的所有函数在文件名和路径无效或不可访问的情况下都会引发 **OSError** ，或者其他具有正确类型但不被操作系统接受的参数。

Python 中的`***os.getcwdb()***`方法是`***os.getcwd()***`方法的字节版。此方法返回当前工作目录(CWD)。

> ***语法:*** os.getcwdb()
> 
> ***参数:*** 不需要参数。
> 
> ***返回类型:*** 这个方法返回一个表示当前工作目录的字节串。

**Code:** Use of os.getcwdb() method to get current working directory

```py
# Python program to explain os.getcwdb() method 

# importing os module 
import os

# Get the current working
# directory (CWD)
cwd = os.getcwdb()

# Print the current working 
# directory (CWD)
print("Current working directory:", cwd)
```

**Output:**

```py
Current working directory: b'/home/ihritik'

```