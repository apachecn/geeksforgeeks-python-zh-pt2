# Python | os.stat()方法

> 原文:[https://www.geeksforgeeks.org/python-os-stat-method/](https://www.geeksforgeeks.org/python-os-stat-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的`***os.stat()***`方法在指定路径上执行 **stat()** 系统调用。此方法用于获取指定路径的状态。

> ***语法:*** os.stat(路径)
> 
> ***参数:***
> **路径**:代表有效路径的字符串或字节对象
> 
> ***返回类型:*** 该方法返回类‘OS . stat _ result’的‘stat _ result’对象，表示指定路径的状态。返回的“stat-result”对象具有以下属性:
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

**代码:**使用 os.stat()方法

```py
# Python program to explain os.stat() method 

# importing os module 
import os

# path
path = '/home/User/Documents/file.txt'

# Get the status of
# the specified path
status = os.stat(path)

# Print the status
# of the specified path
print(status)
```

**Output:**

```py
os.stat_result(st_mode=33188, st_ino=795581, st_dev=2056, st_nlink=1, st_uid=1000,
st_gid=1000, st_size=243, st_atime=1531567080, st_mtime=1530346690, st_ctime=1530346690)

```