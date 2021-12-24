# Python | os.fsync()方法

> 原文:[https://www.geeksforgeeks.org/python-os-fsync-method/](https://www.geeksforgeeks.org/python-os-fsync-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。
***OS . fsync()***Python 中的方法用于强制写入与给定文件描述符相关联的文件。
在这种情况下，我们使用的是文件对象(比如 f)而不是文件描述符，那么我们需要使用 *f.flush()* 然后 os.fsync(f.fileno())来确保与文件对象 f 相关联的所有缓冲区都被写入磁盘。

> **语法:** os.fsync(fd)
> **参数:**
> **fd:** 需要缓冲区同步的文件描述符。
> **返回类型:**此方法不返回任何值。

**代码#1:** 使用 ***os.fsync()*** 方法

## 蟒蛇 3

```
# Python program to explain os.fsync() method

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
# using os.fsync() method
os.fsync(fd)
print("Force write of file committed successfully")

# Close the file descriptor
os.close(fd)
```

**Output:** 

```
Force write of file committed successfully
```

**代码#2:** 如果使用文件对象

## 蟒蛇 3

```
# Python program to explain os.fsync() method

# importing os module
import os

# File path
path = 'file.txt'

# Open the file and get
# the file object
# using open() method
f = open(path, 'w')

# Write a string to
# the file object
str = "GeeksforGeeks"
f.write(str)

# Firstly, flush internal buffers
f.flush()

# Now, sync. all internal buffers
# associated with the file object
# with disk (force write of file)
# using os.fsync() method
os.fsync(f.fileno())

print("Force write of file committed successfully")

# Close the file object
f.close()
```

**Output:** 

```
Force write of file committed successfully
```