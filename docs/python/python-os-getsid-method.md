# Python | os.getsid()方法

> 原文:[https://www.geeksforgeeks.org/python-os-getsid-method/](https://www.geeksforgeeks.org/python-os-getsid-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

os 模块中的所有函数在文件名和路径无效或不可访问的情况下都会引发 **OSError** ，或者其他具有正确类型但不被操作系统接受的参数。

`***os.getsid()***`Python 中的方法用于获取与指定进程 id 关联的进程的会话 id。

**注意:** `***os.getsid()***`方法只在 UNIX 平台上可用。

> ***语法:***OS . get id(PID)
> 
> ***参数:***
> **pid** :表示需要会话 id 的进程的进程 id 的整数值。
> 
> ***返回类型:*** 该方法返回一个整数值，该整数值代表与指定进程 id 相关联的进程的会话 id。

**Code:** Use of os.getsid() method

```
# Python program to explain os.getsid() method 

# importing os module 
import os

# Get the session id
# of the current process
# using os.getsid() method

# 0 as pid represents the
# calling process
pid = 0 
sid = os.getsid(pid)

# Print the session id
# of the current process
print("Session id of the current process:", sid)

pid = 10
# Get the session id
# of the process associated with
# the specified pid
# using os.getsid() method
sid = os.getsid(pid)

# Print the session id
print("Session id of the process whose process id is % d:" % pid, sid)
```

**输出:**
![os.getsid() method output](img/9067de12e39bac3f1da39243ed11a477.png)