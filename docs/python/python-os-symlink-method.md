# Python | os.symlink()方法

> 原文:[https://www.geeksforgeeks.org/python-os-symlink-method/](https://www.geeksforgeeks.org/python-os-symlink-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的`***os.symlink()***`方法用于创建符号链接。此方法创建指向源命名目标的符号链接。
阅读符号链接/软链接，请参考[这篇文章](https://www.geeksforgeeks.org/soft-hard-links-unixlinux/)。

> **语法:** os.symlink(src，dst，target_is_directory = False，* dir _ FD = None)
> 
> **参数:**
> **src:** 表示文件系统路径的类路径对象。这是将为其创建符号链接的源文件路径。
> **dst:** 表示文件系统路径的类似路径的对象。这是将创建符号链接的目标文件路径。
> **target_is_directory** (可选):该参数默认值为 False。如果指定的目标路径是目录，那么它的值应该是真。
> **dir_fd** (可选):引用目录的文件描述符。
> 
> **返回类型:**此方法不返回值。

**代码:**使用`***os.symlink()***`方法

```py
# Python program to explain os.symlink() method 

# importing os module 
import os

# Source file path
src = '/home/ihritik/file.txt'

# Destination file path
dst = '/home/ihritik/Desktop/file(symlink).txt'

# Create a symbolic link
# pointing to src named dst
# using os.symlink() method
os.symlink(src, dst)

print("Symbolic link created successfully")
```

**Output:**

```py
Symbolic link created successfully

```

**参考:**T2】https://docs.python.org/3/library/os.html#os.link