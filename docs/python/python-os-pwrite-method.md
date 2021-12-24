# Python | os.pwrite()方法

> 原文:[https://www.geeksforgeeks.org/python-os-pwrite-method/](https://www.geeksforgeeks.org/python-os-pwrite-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的`***os.pwrite()***`方法用于将指定的字节串写入指定位置与指定文件描述符相关联的文件。任何现有值将在指定位置被覆盖。

一个*文件描述符*是一个小整数值，对应于当前进程已经打开的一个文件。它用于执行各种较低级别的输入/输出操作，如读、写、发送等。

**注意** : `***os.pwrite()***`方法用于低级操作，应该应用于`***os.open()***`或`***os.pipe()***`方法返回的文件描述符。

> ***语法:*** os.pwrite(fd，str，offset)
> 
> ***参数:***
> **fd** :表示待写文件的文件描述符。
> **str** :表示要写入文件的内容的字节串
> **偏移量**:表示起始位置的整数值。文件写入将从该偏移值开始。
> 
> ***返回类型:*** 这个方法返回一个代表实际写入字节数的整数值。。

将以下文本视为名为 *file.txt* 的文件内容。

```py
C, C++, Java, C#, PHP
```

**Code:** Use of os.pwrite() method

```py
# Python program to explain os.pwrite() method

# Importing os module
import os

# Filename
filename = "file.txt"

# Open the file and get the
# file descriptor associated 
# with it using os.open method
fd = os.open(filename, os.O_RDWR)

# String to be written in the file
s = "Python, "

# converting string to bytestring
text = s.encode("utf-8")

# Position from where
# file writing will start 
offset = 0

# As offset is 0, bytestring
# will be written in the 
# beginning of the file

# Write the bytestring
# to the file indicated by 
# file descriptor at 
# specified position
bytesWritten = os.pwrite(fd, text, offset)
print("Number of bytes actually written:", bytesWritten)

# Print the content of the file
with open(filename) as f:
    print(f.read())

# String to be written in the file
s = "Javascript, "

# converting string to bytestring
text = s.encode("utf-8")

# Position from where
# file writing will start 
# os.stat(fd).st_size will return
# file size in bytes
# so bytestring will be written 
# at the end of the file
offset = os.stat(fd).st_size

# Write the bytestring
# to the file indicated by 
# file descriptor at 
# specified position
bytesWritten = os.pwrite(fd, text, offset)
print("\nNumber of bytes actually written:", bytesWritten)

# Print the content of the file
with open(filename) as f:
    print(f.read())

# String to be written in the file
s = "R Programming, "

# converting string to bytestring
text = s.encode("utf-8")

# Position from where
# file writing will start
offset = 10

# Write the bytestring
# to the file indicated by 
# file descriptor at 
# specified position
bytesWritten = os.pwrite(fd, text, offset)
print("\nNumber of bytes actually written:", bytesWritten)

# Print the content of the file
with open(filename) as f:
    print(f.read())
```

**Output:**

```py
Number of bytes actually written: 8
Python, Java, C#, PHP

Number of bytes actually written: 12
Python, Java, C#, PHP
Javascript, 

Number of bytes actually written: 15
Python, JaR Programming, ascript, 

```