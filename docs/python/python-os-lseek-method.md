# Python | os.lseek()方法

> 原文:[https://www.geeksforgeeks.org/python-os-lseek-method/](https://www.geeksforgeeks.org/python-os-lseek-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

`os.lseek()`方法将文件描述符 **fd** 的当前位置设置为给定位置 pos，该位置 pos 由 **how** 修改。

```py
Syntax: os.lseek(fd, pos, how)

Parameters: 
fd:  This is the file descriptor on which seek is to be performed.
pos:  This is the position in the file with respect to given parameter how.
It can accept three values which are 

    *   **os。SEEK_SET** 或 **0** 设置相对于文件开头的位置*   **os。SEEK_CUR** 或 **1** 设置相对于当前位置的位置*   **os。SEEK_END** 或 **2** 设置相对于文件结尾的位置。
how: This is the reference point in the file. It also accepts three values which are

    *   **os。SEEK_SET** 或 **0** 将参考点设置到文件的开头*   **os。SEEK_CUR** 或 **1** 将参考点设置到当前位置*   **os。SEEK_END** 或 **2** 将参考点设置到文件的末尾。

Return Value:  This method does not returns any value.

Example #1 :

Using os.lseek() method to seek the file from beginning

```
# Python program to explain os.lseek() method  

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

# Seek the file from beginning 
# using os.lseek() method 
os.lseek(fd, 0, 0) 

# Read the file 
s = os.read(fd, 13) 

# Print string 
print(s) 

# Close the file descriptor  
os.close(fd) 
```py

   **输出:**  
```

```py
b'GeeksforGeeks'

```

**例 2 :**

使用`os.lseek()`方法来从特定位置

```py
# Python program to explain os.lseek() method 

# importing os module 
import os 

# path 
path =  'C:/Users/Rajnish/Desktop/testfile.txt'

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

# Seek the file after position '2'
# using os.lseek() method
os.lseek(fd, 2, 0)

# Read the file
s = os.read(fd, 11)

# Print string
print(s)

# Close the file descriptor 
os.close(fd)
```

**中寻找文件输出:**

```py
b'eksforGeeks'

```