# Python | os.fstatvfs()方法

> 原文:[https://www.geeksforgeeks.org/python-os-fstatvfs-method/](https://www.geeksforgeeks.org/python-os-fstatvfs-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

`***os.fstatvfs()***`Python 中的方法用于获取包含与给定文件描述符相关联的文件的文件系统的信息。为了获取文件系统信息，该方法在与给定文件描述符相关联的路径上执行*stat fs()*系统调用。

*文件描述符*是对应于文件或其他输入/输出资源(如管道或网络套接字)的小整数值。它是资源的抽象指示符，并作为句柄来执行各种较低级别的输入/输出操作，如读、写、发送等。
**例如:**标准输入通常是值为 0 的文件描述符，标准输出通常是值为 1 的文件描述符，标准错误通常是值为 2 的文件描述符。
当前进程打开的其他文件将获得值 3、4、5 等等。

**注意:** `***os.fstatvfs()***`方法仅在 Unix 平台上可用。

> ***语法*** os.fstatvfs(fd)
> 
> ***参数:***
> **fd** :需要文件系统信息的文件描述符。
> 
> ***返回类型:*** 这个方法返回一个类为“os.statvfs_result”的对象，它的属性表示包含与给定文件描述符相关联的文件的文件系统的信息。
> 返回的 os.statvfs_result 对象具有以下属性:
> 
> *   **f_bsize** :表示文件系统块大小
> *   **f_frsize** :表示碎片大小
> *   **f_blocks** 以 f_frsize 为单位表示 fs 的大小
> *   **f_bfree** :表示空闲块数
> *   **f _ bafail**:代表非特权用户的空闲块数
> *   **f_files** :表示索引节点数
> *   **f_ffree** :表示空闲索引节点数
> *   **f _ fafail**:代表非特权用户的空闲索引节点数
> *   **f_fsid** :表示文件系统 id
> *   **f_flag** :代表挂载标志
> *   **f_namemax** :代表最大文件名长度

**Code:** Use of os.fstatvfs() method to get information about the filesystem containing the file associated with the given file descriptor.

```py
# Python program to explain os.fstatvfs() method 

# importing os module 
import os

# File path 
path = "/home / ihritik / Desktop / file.txt"

# open the file and get
# the file descriptor associated
# with it using os.open() method
fd = os.open(path, os.O_WRONLY)

# get the information about the
# filesystem containing the file
# associated with the given
# file descriptor using os.fstatvfs() method
info = os.fstatvfs(fd)

# Print the information
# about the file system
print(info)

# Print the file system block size
print("File system block size:", info.f_bsize)

# Print the number of free blocks
# in the file system
print("Number of free blocks:", info.f_bfree)

# Close the file descriptor
os.close(fd)
```

**Output:**

```py
os.statvfs_result(f_bsize=4096, f_frsize=4096, f_blocks=59798433, f_bfree=56521834,
f_bavail=53466807, f_files=15261696, f_ffree=14933520, f_favail=14933520, f_flag=4096,
f_namemax=255)
File system block size: 4096
Number of free blocks: 56517297

```