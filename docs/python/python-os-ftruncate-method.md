# Python | os.ftruncate()方法

> 原文:[https://www.geeksforgeeks.org/python-os-ftruncate-method/](https://www.geeksforgeeks.org/python-os-ftruncate-method/)

**Python 中的操作系统模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。
`os.ftruncate()`方法截断文件描述符 **fd** 对应的文件，使其大小最多为长度字节。

> **语法:** os.ftruncate(fd，长度)
> 
> **参数:**
> **fd:** 这是要被截断的文件描述符。
> **长度:**这是要截断的文件的长度。
> 
> **返回值:**此方法不返回值。

**示例#1 :**
使用`os.ftruncate()`方法截断文件

```
# Python program to explain os.ftruncate() method 

# importing os module 
import os 

# path 
path = 'C:/Users/Rajnish/Desktop/testfile.txt'

# Open the file and get
# the file descriptor associated
# with it using os.open() method
fd = os.open(path, os.O_RDWR|os.O_CREAT)

# String to be written
s = 'GeeksforGeeks'

# Convert the string to bytes 
line = str.encode(s)

# Write the bytestring to the file 
# associated with the file 
# descriptor fd 
os.write(fd, line)

# Using os.ftruncate() method
os.ftruncate(fd, 5)

# Seek the file from beginning
# using os.lseek() method
os.lseek(fd, 0, 0)

# Read the file
s = os.read(fd, 15)

# Print string
print(s)

# Close the file descriptor 
os.close(fd)
```

**Output:**

```
b'Geeks'

```

**示例 2 :**
使用`os.ftruncate()`方法截断文件

```
# Python program to explain os.ftruncate() method 

# importing os module 
import os 

# path 
path = 'C:/Users/Rajnish/Desktop/testfile.txt'

# Open the file and get
# the file descriptor associated
# with it using os.open() method
fd = os.open(path, os.O_RDWR|os.O_CREAT)

# String to be written
s = 'GeeksforGeeks - Computer Science portal'

# Convert the string to bytes 
line = str.encode(s)

# Write the bytestring to the file 
# associated with the file 
# descriptor fd 
os.write(fd, line)

# Using os.ftruncate() method
os.ftruncate(fd, 10)

# Seek the file from beginning
# using os.lseek() method
os.lseek(fd, 0, 0)

# Read the file
s = os.read(fd, 15)

# Print string
print(s)

# Close the file descriptor 
os.close(fd)
```

**Output:**

```
b'GeeksforGe'

```