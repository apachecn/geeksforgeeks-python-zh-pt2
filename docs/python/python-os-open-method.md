# Python | os.open()方法

> 原文:[https://www.geeksforgeeks.org/python-os-open-method/](https://www.geeksforgeeks.org/python-os-open-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

`***os.open()***`Python 中的方法用于打开指定的文件路径，根据指定的标志设置各种标志，并根据指定的模式设置其模式。
此方法返回新打开文件的文件描述符。返回的文件描述符是不可继承的。

> **语法:** os.open(路径，标志，模式= 0o777，* dir _ FD =无)
> 
> ***参数:***
> **路径:**表示文件系统路径的类路径对象。这是要打开的文件路径。
> 类路径对象是表示路径的字符串或字节对象。
> **标志:**此参数指定为新打开的文件设置的标志。
> **模式**(可选):代表新打开文件模式的数值。此参数的默认值为 0o777(八进制)。
> **dir_fd** (可选):引用目录的文件描述符。
> 
> ***返回类型:*** 该方法返回新打开文件的文件描述符。

**Code:** Use of `***os.open()***` method to open a file path

```py
# Python program to explain os.open() method 

# importing os module 
import os

# File path to be opened
path = './file9.txt'

# Mode to be set 
mode = 0o666

# flags
flags = os.O_RDWR | os.O_CREAT

# Open the specified file path
# using os.open() method
# and get the file descriptor for 
# opened file path
fd = os.open(path, flags, mode)

print("File path opened successfully.")

# Write a string to the file
# using file descriptor
str = "GeeksforGeeks: A computer science portal for geeks."
os.write(fd, str.encode())
print("String written to the file descriptor.") 

# Now read the file 
# from beginning
os.lseek(fd, 0, 0)
str = os.read(fd, os.path.getsize(fd))
print("\nString read from the file descriptor:")
print(str.decode())

# Close the file descriptor
os.close(fd)
print("\nFile descriptor closed successfully.")
```

**Output:**

```py
File path opened successfully.
String written to the file descriptor.

String read from file descriptor:
GeeksforGeeks: A computer science portal for geeks.

File descriptor closed successfully.

```

**参考:**T2】https://docs.python.org/3/library/os.html#os.open