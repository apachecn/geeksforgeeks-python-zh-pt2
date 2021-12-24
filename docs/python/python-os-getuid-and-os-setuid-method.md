# Python | os.getuid()和 os.setuid()方法

> 原文:[https://www . geesforgeks . org/python-OS-getuid-and-OS-setuid-method/](https://www.geeksforgeeks.org/python-os-getuid-and-os-setuid-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

os 模块中的所有函数在文件名和路径无效或不可访问的情况下都会引发 **OSError** ，或者其他具有正确类型但不被操作系统接受的参数。

Python 中的`***os.getuid()***`方法用于获取当前进程的真实用户 id，而`***os.setuid()***`方法用于设置当前进程的真实用户 id。

**用户 ID** :在类似 Unix 的操作系统中，用户由一个唯一的值标识，该值称为用户 ID。用户标识用于确定用户有权访问哪个系统资源。

**注意:** `***os.setuid()***`和`***os.getuid()***`方法仅在 UNIX 平台上可用，`***os.setuid()***`方法的功能通常只对超级用户可用，因为只有超级用户才能更改用户 id。
超级用户是指拥有运行或执行操作系统中任何程序的所有权限的根用户或管理用户。

**os.getuid()方法**

> ***语法:*** os.getuid()
> 
> ***参数:*** 不需要参数
> 
> ***返回类型:*** 这个方法返回一个代表当前进程真实用户 id 的整数值。

**Code #1:** Use of os.getuid() method

```py
# Python program to explain os.getuid() method 

# importing os module 
import os

# Get the real user ID
# of the current process
# using os.getuid() method
uid = os.getuid()

# Print the real user ID
# of the current process
print("Real user ID of the current process:", uid)
```

**Output:**

```py
Real user ID of the current process: 1000

```