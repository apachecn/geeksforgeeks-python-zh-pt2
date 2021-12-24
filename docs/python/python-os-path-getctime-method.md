# Python | os.path.getctime()方法

> 原文:[https://www . geesforgeks . org/python-OS-path-getctime-method/](https://www.geeksforgeeks.org/python-os-path-getctime-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。 **os.path** 模块是 Python 中 **OS 模块**的子模块，用于公共路径名操作。

Python 中的`***os.path.getctime()***`方法用于获取指定路径的系统 *ctime* 。这里 *ctime* 指的是 *UNIX* 中指定路径的最后一次元数据更改，而在 *Windows* 中，它指的是路径创建时间。
此方法返回一个浮点值，表示自纪元以来的秒数。如果文件不存在或不可访问，此方法将引发**错误。**

**注:**历元代表时间开始的点。它依赖于平台。对于 Unix，纪元是 1970 年 1 月 1 日 00:00:00(世界协调时)。

> *语法:*OS . path . get time(path)
> 
> ***参数:***
> **路径**:表示文件系统路径的类路径对象。类似路径的对象是代表路径的*字符串*或*字节*对象。
> 
> ***返回类型:*** 该方法返回类“float”的浮点值，该值代表指定路径的 ctime(以秒为单位)。

**代码#1:** 使用 os.path.getctime()方法

```py
# Python program to explain os.path.getctime() method 

# importing os and time module 
import os
import time

# Path
path = '/home/User/Documents/file.txt'

# Get the ctime of last
# for the specified path
c_time = os.path.getctime(path)
print("ctime since the epoch:", c_time)

# convert the ctime in
# seconds since epoch
# to local time
local_time = time.ctime(c_time)
print("ctime (Local time):", local_time)
```

**Output:**

```py
ctime since the epoch: 1558447897.3122742
ctime (Local time): Tue May 21 19:41:37 2019

```

**代码#2:** 使用 os.path.getctime()方法时处理错误

```py
# Python program to explain os.path.getctime() method 

# importing os, time and sys module 
import os
import sys
import time

# Path
path = '/home/User/Documents/file2.txt'

# Get the ctime 
# for the specified path
try:
    c_time = os.path.getctime(path)
    print("ctime since the epoch:", c_time)

except OSError:
    print("Path '%s' does not exists or is inaccessible" %path)
    sys.exit()

# convert ctime in
# seconds since epoch
# to local time
local_time = time.ctime(c_time)
print("ctime(Local time):", local_time)

# above code will print
# path does not exists or is inaccessible'
# if the specified path does not
# exists or is inaccessible

```

**Output:**

```py
Path '/home/User/Documents/file2.txt' does not exists or is inaccessible

```

**参考:**T2】https://docs.python.org/3/library/os.path.html