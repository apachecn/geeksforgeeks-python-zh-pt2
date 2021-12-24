# Python | os.readlink()方法

> 原文:[https://www.geeksforgeeks.org/python-os-readlink-method/](https://www.geeksforgeeks.org/python-os-readlink-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

os 模块中的所有函数在文件名和路径无效或不可访问的情况下都会引发 **OSError** ，或者其他具有正确类型但不被操作系统接受的参数。

Python 中的`***os.readlink()***`方法用于解析符号链接。此方法返回符号链接指向的路径。

> ***语法:*** os.readlink(路径，* dir _ FD =无)
> 
> ***参数:***
> **路径**:代表文件路径的类路径对象。类似路径的对象是表示路径的字符串或字节对象。
> **dir_fd** (可选) :引用目录的文件描述符。此参数的默认值为“无”。
> 如果指定的路径是绝对的，那么 dir_fd 被忽略。
> 
> **注意:**参数列表中的“*”表示以下所有参数(在我们的例子中为‘dir _ FD’)都是仅包含关键字的参数，并且可以使用它们的名称来提供，而不是作为位置参数。
> 
> ***返回类型:*** 如果指定路径也是字符串对象，则该方法返回字符串对象，如果指定路径是字节对象，则返回字节对象。返回值表示符号链接指向的路径。

**Code:** Use of os.readlink() method to resolve a symbolic link

```
# Python program to explain os.readlink() method 

# importing os module 
import os

# Original file path
path = "/home/ihritik/Documents/file.txt"

# Create a symbolic link
# of above path 
# using os.symlink() method
link = "/home/ihritik/Desktop/file(symlink).txt"
os.symlink(path, link)

# So, link is a symbolic link
# Now using os.readlink() method
# resolve the symbolic link
originalPath = os.readlink(link)

# print the path to which
# symbolic link points
print("Symbolic link points to", originalPath)

# If the given path is not a
# symbolic link then 
# os.readlink() method will
# raise an OSError
```

**Output:**

```
Symbolic link points to /home/ihritik/Documents/file.txt

```

**参考:**T2】https://docs.python.org/3/library/os.html