# Python | os.rename()方法

> 原文:[https://www.geeksforgeeks.org/python-os-rename-method/](https://www.geeksforgeeks.org/python-os-rename-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

`***os.rename()***`Python 中的方法用于重命名文件或目录。
此方法将源文件/目录重命名为指定的目标文件/目录。

> **语法:** os.rename(源，目标，* src _ dir _ FD =无，dst_dir_fd =无)
> 
> ***参数:***
> **来源:**表示文件系统路径的类路径对象。这是要重命名的源文件路径。
> **目的地:**表示文件系统路径的类似路径的对象。
> **src_dir_fd** (可选):引用目录的文件描述符。
> **dst_dir_fd** (可选):引用目录的文件描述符。
> 
> ***返回类型:*** 此方法不返回值。

**Code #1:** Use of `***os.rename()***` method

```py
# Python program to explain os.rename() method 

# importing os module 
import os

# Source file path
source = 'GeeksforGeeks/file.txt'

# destination file path
dest = 'GeekforGeeks/newfile.txt'

# Now rename the source path
# to destination path
# using os.rename() method
os.rename(source, dest)
print("Source path renamed to destination path successfully.")
```

**Output:**

```py
Source path renamed to destination path successfully.

```

**Code #2:** Handling possible errors

```py
# Python program to explain os.rename() method 

# importing os module 
import os

# Source file path
source = './GeeksforGeeks/file.txt'

# destination file path
dest = './GeeksforGeeks/dir'

# try renaming the source path
# to destination path
# using os.rename() method

try :
    os.rename(source, dest)
    print("Source path renamed to destination path successfully.")

# If Source is a file 
# but destination is a directory
except IsADirectoryError:
    print("Source is a file but destination is a directory.")

# If source is a directory
# but destination is a file
except NotADirectoryError:
    print("Source is a directory but destination is a file.")

# For permission related errors
except PermissionError:
    print("Operation not permitted.")

# For other errors
except OSError as error:
    print(error)
```

**Output:**

```py
Source is a file but destination is a directory.

```

**参考:**T2】https://docs.python.org/3/library/os.html#os.rename