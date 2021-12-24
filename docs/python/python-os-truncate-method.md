# Python | os.truncate()方法

> 原文:[https://www.geeksforgeeks.org/python-os-truncate-method/](https://www.geeksforgeeks.org/python-os-truncate-method/)

**Python 中的操作系统模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。
`os.truncate()`方法截断**路径**对应的文件，使其大小最多为长度字节。该功能也可以支持**文件描述符**。

> **语法:** os.truncate(路径，长度)
> 
> **参数:**
> **路径:**此参数是要截断的文件的路径或文件描述符。
> **长度:**这是要截断的文件的长度。
> 
> **返回值:**此方法不返回值。

**示例#1 :**

使用`os.truncate()`方法使用文件的路径截断文件。

```py
# Python program to explain os.truncate() method 

# importing os module 
import os 

# path 
path = 'C:/Users/Rajnish/Desktop/testfile.txt'

# Open the file and get
# the file descriptor associated
# with it using os.open() method
fd = os.open(path, os.O_RDWR|os.O_CREAT)

# String to be written
s = 'GeeksforGeeks - A Computer Science portal'

# Convert the string to bytes 
line = str.encode(s)

# Write the bytestring to the file 
# associated with the file 
# descriptor fd 
os.write(fd, line)

# Using os.truncate() method
# Using path as parameter
os.truncate(path, 10)

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

```py
b'GeeksforGe'

```

**示例#2 :**
使用`os.truncate()`方法使用文件描述符截断文件

```py
# Python program to explain os.truncate() method 

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

# Using os.truncate() method
# Using fd as parameter
os.truncate(fd, 4)

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

```py
b'Geek'

```