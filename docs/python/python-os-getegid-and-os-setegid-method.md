# Python | os.getegid()和 os.setegid()方法

> 原文:[https://www . geesforgeks . org/python-OS-getegid-and-OS-setegid-method/](https://www.geeksforgeeks.org/python-os-getegid-and-os-setegid-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

os 模块中的所有函数在文件名和路径无效或不可访问的情况下都会引发 **OSError** ，或者其他具有正确类型但不被操作系统接受的参数。

Python 中的`***os.getegid()***`方法用于获取当前流程的有效组 id，`***os.setegid()***`方法用于设置当前流程的有效组 id。

**注意:** `***os.setegid()***`和`***os.getegid()***`方法只在 UNIX 平台上可用，`***os.setegid()***`方法的功能通常只对超级用户可用。
超级用户是指拥有运行或执行操作系统中任何程序的所有权限的根用户或管理用户。

## os.getegid()方法–

> ***语法*** 操作系统.加权()
> 
> ***参数:*** 不需要参数
> 
> ***返回类型:*** 该方法返回一个整数值，代表当前流程的有效组标识。

**Code #1:** Use of os.getegid() method

```py
# Python program to explain os.getegid() method 

# importing os module 
import os

# Get the effective group id
# of the current process
# using os.getegid() method
egid = os.getegid()

# Print the effective group id
# of the current process
print("Effective group id of the current process:", egid)
```

**输出:**
![Output getegid method](img/fda29bc7eb405df0852557a62ed4ec75.png)

## os.setegid()方法–

> ***语法:*** os.setegid(egid)
> 
> ***参数:***
> **egid** :代表当前流程新的有效组 id 的整数值。
> 
> ***返回类型:*** 此方法不返回值。

**Code #2:** Use of os.setegid() method

```py
# Python program to explain os.setegid() method 

# importing os module 
import os

# Get the effective group id
# of the current process
# using os.getegid() method
egid = os.getegid()

# Print the effective group id
# of the current process
print("Effective group id of the current process:", egid)

# Change the effective group id
# for the current process
# using os.setegid() method
egid = 200
os.setegid(egid)
print("Effective group id changed")

# Print the effective group id
# of the current process
egid = os.getegid()
print("Effective group id of the current process:", egid)
```

**输出:**
![setegid method output](img/858700fdd17621de63dfc03c35d9d560.png)