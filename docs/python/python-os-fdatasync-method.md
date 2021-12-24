# Python | os.fdatasync()方法

> 原文:[https://www.geeksforgeeks.org/python-os-fdatasync-method/](https://www.geeksforgeeks.org/python-os-fdatasync-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的`***os.fdatasync()***`方法用于强制写入与给定文件描述符相关联的文件。与`***os.fsync()***`方法不同，它不强制更新元数据。
`***os.fdatasync()***`方法比`***os.fsync()***`方法更快，因为它只需要强制一个磁盘写入，而不是两个。

> **语法:T1 操作系统. fdatasync(fd)**
> 
> **参数:**
> **fd:** 要写入数据的文件描述符。
> 
> **返回类型:**此方法不返回值。

**代码:**使用`***os.fdatasync()***`方法

```py
# Python program to explain os.fdatasync() method 

# importing os module 
import os

# File path
path = 'file.txt'

# Open the file and get
# the file descriptor 
# associated with 
# using os.open() method
fd = os.open(path, os.O_RDWR)

# Write a bytestring
str = b"GeeksforGeeks" 

os.write(fd, str)

# The written string is
# available in program buffer
# but it might not actually 
# written to disk until
# program is closed or 
# file descriptor is closed. 

# sync. all internal buffers
# associated with the file descriptor
# with disk (force write of file)
# using os.fdatasync() method
os.fdatasync(fd)
print("Force write of file committed successfully")

# Close the file descriptor 
os.close(fd)

# os.fdatasync() method
# does not force update of
# metadata. if you want to 
# update it too, use
# os.fsync() method instead. 
```

**Output:**

```py
Force write of file committed successfully

```

**参考:**T2】https://docs.python.org/3/library/os.html#os.fdatasync