# Python | os.getgid()和 os.setgid()方法

> 原文:[https://www . geesforgeks . org/python-OS-getgid-and-OS-setgid-method/](https://www.geeksforgeeks.org/python-os-getgid-and-os-setgid-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

os 模块中的所有函数在文件名和路径无效或不可访问的情况下都会引发 **OSError** ，或者其他具有正确类型但不被操作系统接受的参数。

Python 中的`***os.getgid()***`方法用于获取当前进程的真实组 id，`***os.setgid()***`方法用于设置当前进程的真实组 id。

**注:**`***os.setgid()***``***os.getgid()***`方法仅在 UNIX 平台上可用。

**os.getgid()方法**

> ***语法:*** os.getgid()
> 
> ***参数:*** 不需要参数
> 
> ***返回类型:*** 这个方法返回一个整数值，代表当前进程的真实组 id。

**Code #1:** Use of os.getgid() method

```
# Python program to explain os.getgid() method 

# importing os module 
import os

# Get the group id
# of the current process
# using os.getgid() method
gid = os.getgid()

# Print the group ID
# of the current process
print("Group id of the current process:", gid)
```

**Output:**

```
Group id of the current process: 1000

```

![Getgid method terminal output](img/2b3e097fb36f604b3150eae0be442baa.png)

**os.setgid()方法**

> ***语法:*** os.setgid(euid)
> 
> ***参数:***
> **euid** :代表当前流程新组 id 的整数值。
> 
> ***返回类型:*** 此方法不返回值。

**Code #2:** Use of os.setgid() method

```
# Python program to explain os.setgid() method 

# importing os module 
import os

# Get the group id
# of the current process
# using os.getgid() method
gid = os.getgid()

# Print the real group id
# of the current process
print("Group id of the current process:", gid)

# Change the group id
# of the current process
# using os.setgid() method
gid = 23
os.setgid(gid)
print("Group id changed")

# Print the group id
# of the current process
gid = os.getgid()
print("Group id of the current process:", gid)
```

**Output:**

```
Group id of the current process: 0
Group id changed
Group id of the current process: 23

```

![Setgid method terminal output](img/e53c4ad9f4016c271930a11f25cf6a5f.png)