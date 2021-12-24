# Python | os.path.getatime()方法

> 原文:[https://www . geesforgeks . org/python-OS-path-geta time-method/](https://www.geeksforgeeks.org/python-os-path-getatime-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。 **os.path** 模块是 Python 中 **OS 模块**的子模块，用于公共路径名操作。

`***os.path.getatime()***`Python 中的方法用于获取指定路径的最后访问时间。此方法返回一个浮点值，表示自纪元以来的秒数。如果文件不存在或不可访问，此方法将引发**或**。

**注:**历元代表时间开始的点。它依赖于平台。对于 Unix，纪元是 1970 年 1 月 1 日 00:00:00(世界协调时)。

> ***语法:*** os.path.getatime(路径)
> 
> ***参数:***
> **路径**:表示文件系统路径的类路径对象。类似路径的对象是代表路径的*字符串*或*字节*对象。
> 
> ***返回类型:*** 此方法返回类“float”的浮点值，该值代表指定路径最后一次访问的时间(秒)。

**代码#1:** 使用 os.path.getatime()方法

```py
# Python program to explain os.path.getatime() method 

# importing os and time module 
import os
import time

# Path
path = '/home/User/Documents/file.txt'

# Get the time of last
# access of the specified
# path since the epoch
access_time = os.path.getatime(path)
print("Last access time since the epoch:", access_time)

# convert the time in
# seconds since epoch
# to local time
local_time = time.ctime(access_time)
print("Last access time(Local time):", local_time)
```

**Output:**

```py
Last access time since the epoch: 1558447897.0442736
Last access time (Local time): Tue May 21 19:41:37 2019

```

**代码#2:** 使用 os.path.getatime()方法时处理错误

```py
# Python program to explain os.path.getatime() method 

# importing os, time and sys module 
import os
import sys
import time

# Path
path = '/home/User/Documents/file2.txt'

# Get the time of last
# access of the specified
# path since the epoch
try:
    access_time = os.path.getatime(path)
    print("Last access time since the epoch:", access_time)

except OSError:
    print("Path '%s' does not exists or is inaccessible" %path)
    sys.exit()

# convert the time in
# seconds since epoch
# to local time
local_time = time.ctime(access_time)
print("Last access time(Local time):", local_time)

# above code will print
# 'File does not exists or is inaccessible'
# if the specified path does not
# exists or is inaccessible

```

**Output:**

```py
Path '/home/User/Documents/file2.txt' does not exists or is inaccessible

```

**参考:**T2】https://docs.python.org/3/library/os.path.html