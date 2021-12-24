# Python | os.fsencode()方法

> 原文:[https://www.geeksforgeeks.org/python-os-fsencode-method/](https://www.geeksforgeeks.org/python-os-fsencode-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的`***os.fsencode()***`方法用于将指定的文件名编码到文件系统编码中，在 Windows 上用‘*代替‘*’错误处理程序，或‘*严格的‘*’；

> ***语法:*** os.fsencode(文件名)
> 
> ***参数:***
> **文件名**:表示文件系统路径的类路径对象。类路径对象是表示路径的字符串或字节对象。
> 
> ***返回类型:*** 这个方法返回一个代表编码文件名的字节串。

**代码:**使用 os.fsencode()方法

```py
# Python program to explain os.fsencode() method 

# importing os module 
import os

# Filename
filename = "/home/user/File.txt"

# Encode the filename
# to the filesystem encoding   
# with 'surrogateescape' error handler,
# or 'strict' (On Windows)
encode = os.fsencode(filename)

# Print the encoded filename
print(encode)

# The encode filename can be 
# decoded using os.fsdecode() method
print(os.fsdecode(encode))
```

**Output:**

```py
Encoded filename: b'/home/user/F\xc3\x8e\xe2\x95\x9a\xc3\x88.txt'
/home/user/FÎ?È.txt

```

**参考:**T2】https://docs.python.org/3/library/os.html#os.fsencode