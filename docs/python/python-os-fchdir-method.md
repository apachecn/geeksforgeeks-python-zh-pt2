# Python | os.fchdir()方法

> 原文:[https://www.geeksforgeeks.org/python-os-fchdir-method/](https://www.geeksforgeeks.org/python-os-fchdir-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的`***os.fchdir()***`方法用于将当前工作目录更改为给定文件描述符所表示的目录。

*文件描述符*是对应于文件或其他输入/输出资源(如管道或网络套接字)的小整数值。文件描述符是资源的抽象指示符，并作为句柄来执行各种低级输入/输出操作，如读、写、发送等。

**例如:**标准输入通常是值为 0 的文件描述符，标准输出通常是值为 1 的文件描述符，标准错误通常是值为 2 的文件描述符。
由当前进程打开的其他文件将获得值 3、4、5 等等。

`***os.fchdir()***`法相当于`***[os.chdir(file_descriptor)](https://www.geeksforgeeks.org/python-os-chdir-method/)***`法。

> ***语法:*** os.fchdir(fd)
> 
> ***参数:***
> **fd** :一个文件描述符。文件描述符必须代表打开的目录，而不是打开的文件。
> 
> ***返回类型:*** 此方法不返回值。

**Code #1:** Use of os.fchdir() method to change the current working directory

```py
# Python program to explain os.fchdir() method 

# importing os module 
import os

# Print the current working
# directory using os.getcwd() method
print("Current working directory:", os.getcwd()) 

# Path
path = "/home/ihritik/Documents"

# open the directory represented by
# the above given path and get
# the file descriptor associated
# with it using os.open() method
fd = os.open(path, os.O_RDONLY)

# Change the current working
# directory using os.fchdir() method 
os.fchdir(fd)
print("Current working directory changed") 

# Print the current working
# directory using os.getcwd() method
print("Current working directory:", os.getcwd()) 
```

**Output:**

```py
Current working directory: /home/ihritik
Current working directory changed
Current working directory: /home/ihritik/Documents

```

**Code #2:** Possible errors while using of os.fchdir() method

```py
# Python program to explain os.fchdir() method 

# importing os module 
import os

# Path
path = "/home/ihritik/Documents/file.txt"

# open the above path and get
# the file descriptor associated
# with it using os.open() method
fd = os.open(path, os.O_RDONLY)

# The file descriptor must 
# represent an open file 
# instead of an opened directory
# The method will raise 
# 'NotADirectoryError' exception 

# Change the current working
# directory using os.fchdir() method 
os.fchdir(fd)
print("Current working directory changed") 

# Print the current working
# directory using os.getcwd() method
print("Current working directory:", os.getcwd()) 
```

**Output:**

```py
Traceback (most recent call last):
  File "changeDir.py", line 24, in 
    os.fchdir(fd)
NotADirectoryError: [Errno 20] Not a directory

```

**Code #3:** Handling possible errors while using of os.fchdir() method

```py
# Python program to explain os.fchdir() method 

# importing os module 
import os

# Path
path = "/home/ihritik/Desktop/file.txt"

# try opening the above path and get
# the file descriptor associated
# with it using os.open() method
try :
    fd = os.open(path, os.O_RDONLY)

    # Try Changing the current working
    # directory using os.fchdir() method 
    try :
        os.fchdir(fd)
        print("Current working directory changed") 

        # Print the current working
        # directory using os.getcwd() method
        print("Current working directory:", os.getcwd()) 

    # Catch exceptions
    # If file descriptor does
    # not represents a directory
    except NotADirectoryError:
        print("The given file descriptor does \
not represent a directory")

# Catch exceptions
# If path does not exists
except FileNotFoundError:
    print("Path does not exists")

# If there is any permission
# related issue while opening
# the given path 
except PermissionError:
    print("Permission denied")
```

**Output:**

```py
The given file descriptor does not represent a directory

```