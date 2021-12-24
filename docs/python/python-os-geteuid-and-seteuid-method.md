# Python | os.geteuid()和 seteuid()方法

> 原文:[https://www . geesforgeks . org/python-OS-geteuid-and-seteuid-method/](https://www.geeksforgeeks.org/python-os-geteuid-and-seteuid-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

os 模块中的所有函数在文件名和路径无效或不可访问的情况下都会引发 **OSError** ，或者其他具有正确类型但不被操作系统接受的参数。

Python 中的`***os.geteuid()***`方法用于获取当前流程的有效用户 id，而`***os.seteuid()***`方法用于设置当前流程的有效用户 id。

**有效用户 ID** :正常情况下与真实用户 ID 相同，但更改为允许非特权用户访问只能由 root 访问的文件。大多数访问检查都使用有效的用户标识。它还被用作进程创建的文件的所有者。

**注意:** `***os.seteuid()***`和`***os.geteuid()***`方法仅在 UNIX 平台上可用，`***os.seteuid()***`方法的功能通常只对超级用户可用，因为只有超级用户才能更改用户 id。
超级用户是指拥有运行或执行操作系统中任何程序的所有权限的根用户或管理用户。

**os.geteuid()方法**

> *语法:*OS . get uid()
> 
> ***参数:*** 不需要参数
> 
> ***返回类型:*** 该方法返回一个整数值，代表当前进程的有效用户 id。

**Code #1:** Use of os.geteuid() method

```py
# Python program to explain os.geteuid() method 

# importing os module 
import os

# Get the effective user ID
# of the current process
# using os.geteuid() method
euid = os.geteuid()

# Print the effective user ID
# of the current process
print("Effective user ID of the current process:", euid)
```

**Output:**

```py
Effective user ID of the current process: 1000

```