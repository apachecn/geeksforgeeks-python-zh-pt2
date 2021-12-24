# Python | os.pread()方法

> 原文:[https://www.geeksforgeeks.org/python-os-pread-method/](https://www.geeksforgeeks.org/python-os-pread-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的`***os.pread()***`方法用于在给定偏移值的位置从与给定文件描述符相关联的文件中读取最多 *n* 个字节。

如果在从给定文件描述符中读取字节时已经到达文件的末尾，`***os.pread()***`方法将为所有剩余的待读取字节返回一个空字节对象，并且它不影响文件偏移值。

一个*文件描述符*是一个小整数值，对应于当前进程已经打开的一个文件。它用于执行各种较低级别的输入/输出操作，如读、写、发送等。

**注意** : `***os.pread()***`方法用于低级操作，应该应用于`***os.open()***`或`***os.pipe()***`方法返回的文件描述符。

> ***语法:*** os.pread(fd，n，offset)
> 
> ***参数:***
> **fd** :表示待读取文件的文件描述符。
> **n** :表示从与给定文件描述符 fd 相关联的文件中读取的字节数的整数值。
> **偏移量**:表示偏移字节的整数值。
> 
> ***返回类型:*** 该方法返回一个字节串，该字节串代表在给定偏移值的位置从与文件描述符 fd 相关联的文件中读取的字节。

将以下文本视为名为 *Python_intro.txt* 的文件内容。

> Python 是一种广泛使用的通用高级编程语言。它最初由吉多·范·罗苏姆在 1991 年设计，由 Python 软件基金会开发。它主要是为了强调代码的可读性而开发的，它的语法允许程序员用更少的代码行来表达概念。Python 是一种编程语言，可以让您快速工作并更高效地集成系统。

**Code:** Use of os.pread() method

```py
# Python program to explain os.pread() method 

# importing os module 
import os

# Open the file and get
# the file descriptor associated
# with it using os.open() method
fd = os.open("Python_intro.txt", os.O_RDONLY)

# Number of bytes to be read
n = 50

# Read at most n bytes from 
# file descriptor fd
# using os.read() method
readBytes = os.read(fd, n)

# Print the bytes read
print(readBytes)

# Now set the Offset value 
offset = 20

# Read at most n bytes from 
# file descriptor fd at a position of
# given offset value using os.pread() method
readBytes = os.pread(fd, n, offset)

# Print the bytes read
print(readBytes)

# close the file descriptor
os.close(fd)
```

**Output:**

```py
b'Python is a widely used general-purpose, high leve'
b'sed general-purpose, high level programming langua'

```