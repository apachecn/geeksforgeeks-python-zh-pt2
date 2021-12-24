# Python | os.utime()方法

> 原文:[https://www.geeksforgeeks.org/python-os-utime-method/](https://www.geeksforgeeks.org/python-os-utime-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中 **os 模块**的`***os.utime()***`方法用于设置指定路径的访问和修改时间。

> ***语法:*** os.utime(路径，时间=无，*，[ns，]dir_fd =无，follow_symlinks =真)
> 
> ***参数:***
> **路径**:代表有效文件系统路径的字符串或字节对象。
> **次**(可选):一个 2 元组的形式(atime，mtime)，其中每个成员都是一个整数或浮点值，分别表示访问时间和修改时间(以秒为单位)。
> **ns** (可选):一个 2 元组的形式(atime_ns，mtime_ns)，其中每个成员都是一个整数或浮点值，分别表示以纳秒为单位的访问时间和修改时间。
> **dir_fd:** 引用目录的文件描述符。此参数的默认值为“无”。
> **follow _ symlink:**真或假的布尔值。如果为真，方法将跟随符号链接，否则不跟随。
> 
> ***返回类型:*** 此方法不返回值

**代码#1:** 使用`***os.utime()***`方法

```py
# Python program to explain os.utime() method 

# importing os module 
import os

# Path
path = '/home / ihritik / Documents / file.txt'

# Print current access and modification time
# of the above specified path
print("Current access time:", os.stat(path).st_atime)
print("Current modification time:", os.stat(path).st_mtime)

# Access time in seconds
atime = 200000000

# Modification time in seconds
mtime = 100000000

# Set the access time and 
# modification time for the
# above specified path
# using os.utime() method
tup = (atime, mtime)
os.utime(path, tup)

print("\nAccess and modification time changed\n")

# Print current access and modification time
print("Current access time:", os.stat(path).st_atime)
print("Current modification time:", os.stat(path).st_mtime)

# Either we can specify times
# or specify ns parameter.
# It is an error to specify
# tuples for both times and ns
```

**Output:**

```py
Current access time (in seconds): 1568930018.710342
Current modification time (in seconds): 1568930018.610892

Access and modification time changed

Current access time (in seconds): 200000000.0
Current modification time (in seconds): 100000000.0

```

**代码#2:** 如果指定了 ns 参数，

```py
# Python program to explain os.utime() method 

# importing os module 
import os

# Path
path = '/home / ihritik / Documents / file.txt'

# Print current access and modification time
# of the above specified path
print("Current access time (in seconds):", os.stat(path).st_atime)
print("Current modification time (in seconds):", os.stat(path).st_mtime)

# Access time in nanoseconds
atime_ns = 20000000012345

# Modification time in nanoseconds
mtime_ns = 10000000012345

# Set the access time and 
# modification time in nanoseconds 
# for the above specified path
# using os.utime() method
# (ns is keyword only argument) 
tup = (atime_ns, mtime_ns)
os.utime(path, ns = tup)

print("\nAccess and modification time changed\n")

# Print current access and modification time
print("Current access time (in seconds):", os.stat(path).st_atime)
print("Current modification time (in seconds):", os.stat(path).st_mtime)

# Either we can specify times
# or specify ns parameter.
# It is an error to specify
# tuples for both times and ns
```

**Output:**

```py
Current access time (in seconds): 1568930018.710342
Current modification time (in seconds): 1568930018.610892

Access and modification time changed

Current access time (in seconds): 20000.000012345
Current modification time (in seconds): 10000.000012345

```

**代码#3:** 如果时间参数为无且 ns 参数未指定

```py
# Python program to explain os.utime() method 

# importing os module 
import os

# Path
path = '/home / ihritik / Documents / file.txt'

# Print current access and modification time
# of the above specified path
print("Current access time (in seconds):", os.stat(path).st_atime)
print("Current modification time (in seconds):", os.stat(path).st_mtime)

# Set the access time and 
# modification time in nanoseconds 
# for the above specified path
# using os.utime() method
os.utime(path)

print("\nAccess and modification time changed\n")

# Print current access and modification time
print("Current access time (in seconds):", os.stat(path).st_atime)
print("Current modification time (in seconds):", os.stat(path).st_mtime)

# If times is None and ns is unspecified,
# then it will be equivalent to
# specifying ns = (atime_ns, mtime_ns)
# where member atime_ns and mtime_ns
# are current time in nanoseconds 
```

**Output:**

```py
Current access time (in seconds): 20000.000012345
Current modification time (in seconds): 10000.000012345

Access and modification time changed

Current access time (in seconds): 1568930018.710342
Current modification time (in seconds): 1568930018.610892

```

**参考:**T2】https://docs.python.org/3/library/os.html#os.utime