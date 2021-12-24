# Python | os.getcwd()方法

> 原文:[https://www.geeksforgeeks.org/python-os-getcwd-method/](https://www.geeksforgeeks.org/python-os-getcwd-method/)

**Python 中的操作系统模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。
如果文件名和路径无效或不可访问，或者其他参数具有正确的类型，但不被操作系统接受，操作系统模块中的所有功能都会引发 **OSError** 。
`os.getcwd()`方法告诉我们当前工作目录的位置(CWD)。

> **语法:T1 操作系统. getcwd()**
> 
> **参数:**不需要参数。
> 
> **返回值:**这个方法返回一个代表当前工作目录的字符串。

**示例#1 :**

使用`os.getcwd()`方法获取当前工作目录

```
# Python program to explain os.getcwd() method 

# importing os module 
import os 

# Get the current working 
# directory (CWD) 
cwd = os.getcwd() 

# Print the current working  
# directory (CWD) 
print("Current working directory:", cwd) 
```

**Output:**

```
Current working directory: C:\Users\Rajnish\AppData\Local\Programs\Python\Python37

```

**例 2 :**
使用`os.getcwd()`方法获取 GeeksforGeeks 的当前工作目录，即**根**

```
# Python program to explain os.getcwd() method 

# importing os module 
import os 

# Get the current working 
# directory (CWD) 
cwd = os.getcwd() 

# Print the current working  
# directory (CWD) 
# which is root in this case
print("Current working directory:", cwd) 
```

**Output:**

```
Current working directory: /

```