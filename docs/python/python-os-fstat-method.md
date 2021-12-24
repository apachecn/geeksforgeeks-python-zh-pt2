# Python | os.fstat()方法

> 原文:[https://www.geeksforgeeks.org/python-os-fstat-method/](https://www.geeksforgeeks.org/python-os-fstat-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的`***os.fstat()***`方法用于获取文件描述符的状态。
文件描述符是一个小整数值，对应于当前进程已经打开的文件。
文件描述符表示资源，并作为句柄来执行各种低级输入/输出操作，如读、写、发送等。
**例如:**标准输入通常是值为 0 的文件描述符，标准输出通常是值为 1 的文件描述符，标准错误通常是值为 2 的文件描述符。
当前进程打开的其他文件将获得值 3、4、5 等等。

`***os.fstat()***`法相当于`***[os.stat(fd)](https://www.geeksforgeeks.org/python-os-stat-method/)***`法。

> ***语法:*** os.fstat(fd)
> 
> ***参数:***
> **fd** :一个文件描述符。
> 
> ***返回类型:*** 这个方法返回一个类 os 的 stat_result 对象，它代表给定文件描述符的状态。
> 返回的“stat_result”对象是一个元组，具有以下命名属性:
> 
> *   **st_mode** :表示文件类型和文件模式位(权限)。
> *   **st_ino** :表示 Unix 上的索引节点号，Windows 平台上的文件索引。
> *   **st_dev** :表示该文件所在设备的标识。
> *   **st_nlink** :表示硬链接数。
> *   **st_uid** :表示文件所有者的用户标识。
> *   **st_gid** :表示文件所有者的组标识。
> *   **st_size** :表示文件的大小，以字节为单位。
> *   **st_atime** :表示最近一次访问的时间。用秒来表示。
> *   **st_mtime** :表示最近一次内容修改的时间。用秒来表示。
> *   **st_ctime** :表示 Unix 上最近一次元数据更改的时间和 Windows 上的创建时间。用秒来表示。
> *   **st_atime_ns** :与 **st_atime** 相同，但时间以纳秒为单位表示为整数。
> *   **st_mtime_ns** :与 **st_mtime** 相同，但时间以纳秒为单位表示为整数。
> *   **st_ctime_ns** :与 **st_ctime** 相同，但时间以纳秒为单位表示为整数。
> *   **st_blocks** :表示分配给文件的 512 字节块数。
> *   **st_rdev** :表示设备类型，如果是 inode 设备。
> *   **st_flags** :表示文件的用户自定义标志。
> 
> **注**:部分属性依赖于平台，受可用性限制。

**代码:**使用 os.fstat()方法获取文件描述符的状态

```py
# Python program to explain os.fstat() method 

# importing os module 
import os

# Path
path = "/home / ihritik / Desktop / file1.txt"

# open the file represented by
# the above given path and get
# the file descriptor associated
# with it using os.open() method
fd = os.open(path, os.O_RDONLY)

# Get the status of the 
# file descriptor using
# os.fstat() method
status = os.fstat(fd)

# Print the status of
# the file descriptor 
print(status)

# close the file descriptor
os.close(fd)
```

**Output:**

```py
os.stat_result(st_mode=33188, st_ino=801111, st_dev=2056, st_nlink=1, st_uid=1000,
st_gid=1000, st_size=6550, st_atime=1560377051, st_mtime=1560377051, st_ctime=1560377051)

```