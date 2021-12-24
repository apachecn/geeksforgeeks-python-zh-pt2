# Python | os.sendfile()方法

> 原文:[https://www.geeksforgeeks.org/python-os-sendfile-method/](https://www.geeksforgeeks.org/python-os-sendfile-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的`***os.sendfile()***`方法用于从指定的偏移量开始，将指定数量的字节从指定的*源*文件描述符复制到指定的*目的地*文件描述符。
此方法返回发送的字节总数，如果达到 EOF(文件结束)，则返回 0。

> ***语法:*** os.sendfile(目的地、来源、偏移量、计数)
> 
> ***参数:***
> **dest:** 表示目的文件的文件描述符。
> **来源:**代表源文件的文件描述符
> **偏移量:**代表起始位置的整数值。要发送的字节将从该位置开始计数。
> **计数:**表示从源文件描述符发送的字节总数的整数值。
> 
> ***返回类型:*** 这个方法返回一个整数值，代表从源文件描述符发送到目标文件描述符的字节总数。如果达到电渗流，则返回 0。

将以下文本视为名为*‘Python _ intro . txt’*的文件内容。

> Python 是一种广泛使用的通用高级编程语言。它最初由吉多·范·罗苏姆在 1991 年设计，由 Python 软件基金会开发。它主要是为了强调代码的可读性而开发的，它的语法允许程序员用更少的代码行来表达概念。Python 是一种编程语言，可以让您快速工作并更高效地集成系统。

**Code:** Use of `***os.sendfile()***` method

```
# Python program to explain os.sendfile() method 

# importing os module 
import os

# Source file path
source = './Python_intro.txt'

# destination file path
dest = './newfile.txt'

# Open both files and get
# the file descriptor
# using os.open() method
src_fd = os.open(source, os.O_RDONLY)
dest_fd = os.open(dest, os.O_RDWR | os.O_CREAT)

# Now send n bytes from
# source file descriptor
# to destination file descriptor
# using os.sendfile() method
offset = 0
count = 100
bytesSent = os.sendfile(dest_fd, src_fd, offset, count)
print("% d bytes sent / copied successfully." % bytesSent)

# Now read the sent / copied
# content from destination
# file descriptor 
os.lseek(dest_fd, 0, 0)
str = os.read(dest_fd, bytesSent)

# Print read bytes
print(str)

# Close the file descriptors
os.close(src_fd)
os.close(dest_fd)
```

**Output:**

```
100 bytes sent/copied successfully.
b'Python is a widely used general-purpose, high level programming language.
It was initially designed '

```

**参考:**T2】https://docs.python.org/3/library/os.html#os.sendfile