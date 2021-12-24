# Python | os.link()方法

> 原文:[https://www.geeksforgeeks.org/python-os-link-method/](https://www.geeksforgeeks.org/python-os-link-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。
***os.link()*** 方法在 Python 中是用来创建硬链接的。此方法创建指向名为*目的地*的*源*的硬链接。
关于硬链接的阅读，请参考[这篇文章](https://www.geeksforgeeks.org/soft-hard-links-unixlinux/)。

**注意:**此方法仅在 Windows 和 Unix 平台上可用。

> **语法:** os.link(src，dst，* src _ dir _ FD = None，dst_dir_fd = None，follow _ symlink = True)
> **参数:**
> **src:** 表示文件系统路径的类路径对象。这是将为其创建硬链接的源文件路径
> **dst:** 表示文件系统路径的类似路径的对象。这是将创建硬链接的目标文件路径。
> 类路径对象是表示路径的字符串或字节对象。
> **src_dir_fd** (可选):引用目录的文件描述符。此参数的默认值为“无”。如果指定的 src 路径是绝对的，则忽略该参数。如果指定的 src 路径是相对的，并且 src_dir_fd 不是无，则指定的 src 路径是相对于与 src_dir_fd 相关联的目录的。
> **dst_dir_fd** (可选):引用目录的文件描述符。
> **follow _ symlink**(可选) :布尔值。
> **返回类型:**此方法不返回任何值。

**代码:**使用 ***os.link()*** 方法

## 蟒蛇 3

```
# Python program to explain os.link() method

# importing os module
import os

# Source file path
src = '/home/ihritik/file.txt'

# Destination file path
dst = '/home/ihritik/Desktop/file(link).txt'

# Create a hard link
# pointing to src named dst
# using os.link() method
os.link(src, dst)

print("Hard link created successfully")
```

**Output:** 

```
Hard link created successfully
```

**参考:**T2https://docs.python.org/3/library/os.html#os.link