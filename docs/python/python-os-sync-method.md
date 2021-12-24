# Python | os.sync()方法

> 原文:[https://www.geeksforgeeks.org/python-os-sync-method/](https://www.geeksforgeeks.org/python-os-sync-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。
***【OS . sync()】***Python 中的方法用于强制将所有内容写入磁盘。此方法允许进程将所有脏缓冲区刷新到磁盘。
*****OS . sync()********OS . fsync(FD)*****和*****OS . fdata sync(FD)*****方法**–
***OS . sync()***方法强制将所有内容写入磁盘的何处
**注意:**此方法仅在 Unix 平台上可用。**** 

> ******语法:**OS . sync()
> T3】参数:不需要参数。
> **返回类型:**此方法不返回值。****

******代码:**使用 ***os.sync()*** 方法**** 

## ****蟒蛇 3****

```py
**# Python program to explain os.sync() method

# importing os module
import os

# File path 1
path1 = 'file.txt'

# File path 2
path2 = 'file2.txt'

# File path 3
path3 = 'file3.txt'

# Open the files and get
# the file descriptors
# associated with them
# using os.open() method
fd1 = os.open(path1, os.O_RDWR)
fd2 = os.open(path2, os.O_RDWR)
fd3 = os.open(path3, os.O_RDWR)

# Write a bytestring
str = b"GeeksforGeeks"
os.write(fd1, str)
os.write(fd2, str)
os.write(fd3, str)

# Sync. all buffers to disk
# i.e force write everything
# to disk using os.sync() method
os.sync()
print("Force write everything committed successfully")

# Close the file descriptors
os.close(fd1)
os.close(fd2)
os.close(fd3)

# os.sync() method
# will flush all buffers
# to disk.
# it may take a significant
# length of time**
```

******Output:** 

```py
Force write of everything committed successfully
```**** 

******参考:**T2https://docs.python.org/3/library/os.html#os.sync****