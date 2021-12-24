# Python | os.fsdecode()方法

> 原文:[https://www.geeksforgeeks.org/python-os-fsdecode-method/](https://www.geeksforgeeks.org/python-os-fsdecode-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的`***os.fsdecode()***`方法用于从文件系统编码中解码指定的文件名，在 Windows 上用“*替代“T2”的错误处理程序，或“*严格的*；*

> ***语法:*** os.fsdecode(文件名)
> 
> ***参数:***
> **文件名**:表示编码文件的类路径对象。类路径对象是表示路径的字符串或字节对象。
> 
> ***返回类型:*** 这个方法返回一个代表解码文件名的字符串。

**代码:**使用 os.fsdecode()方法

```py
# Python program to explain os.fsdecode() method 

# importing os module 
import os

# Filename encoded to the filesystem encoding
# with 'surrogateescape' error handler
# or 'strict' error handler
filename = b"/home / user / F\xc3\x8e\xe2\x95\x9a\xc3\x88.txt"

# Decode the above filename
# form the filesystem encoding   
# with 'surrogateescape' error handler,
# or 'strict' (On Windows)
decode = os.fsdecode(filename)

# Print the decoded filename
print("Decoded filename:", decode)

# To encode a filename to the filesystem 
# encoding with 'surrogateescape' error handler
# or 'strict' error handler os.encode() method
# can be used
```

**Output:**

```py
Encoded filename: b'/home/user/F\xc3\x8e\xe2\x95\x9a\xc3\x88.txt'
Decoded filename: /home/user/FÎ?È.txt

```

**参考:**T2】https://docs.python.org/3/library/os.html#os.fsdecode