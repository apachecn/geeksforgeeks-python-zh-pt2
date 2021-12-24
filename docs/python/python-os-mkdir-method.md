# Python | os.mkdir()方法

> 原文:[https://www.geeksforgeeks.org/python-os-mkdir-method/](https://www.geeksforgeeks.org/python-os-mkdir-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

os 模块中的所有函数在文件名和路径无效或不可访问的情况下都会引发 **OSError** ，或者其他具有正确类型但不被操作系统接受的参数。

Python 中的`***os.mkdir()***`方法用于创建指定数值模式的名为 path 的目录。如果要创建的目录已经存在，此方法将引发[文件存在错误](https://docs.python.org/3/library/exceptions.html#FileExistsError)。

> ***语法:*** os.mkdir(path，mode = 0o777，*，dir_fd = None)
> 
> ***参数:***
> **路径**:表示文件系统路径的类路径对象。类似路径的对象是表示路径的字符串或字节对象。
> **模式**(可选) :表示待创建目录模式的整数值。如果省略该参数，则使用默认值 Oo777。
> **dir_fd** (可选) :引用目录的文件描述符。此参数的默认值为“无”。
> 如果指定的路径是绝对的，那么 dir_fd 被忽略。
> 
> **注意:**参数列表中的“*”表示以下所有参数(在我们的例子中为‘dir _ FD’)都是仅包含关键字的参数，并且可以使用它们的名称来提供，而不是作为位置参数。
> 
> ***返回类型:*** 此方法不返回值。

**Code #1:** Use of os.mkdir() method to create directory/file

```
# Python program to explain os.mkdir() method 

# importing os module 
import os

# Directory
directory = "GeeksForGeeks"

# Parent Directory path
parent_dir = "/home/User/Documents"

# Path
path = os.path.join(parent_dir, directory)

# Create the directory
# 'GeeksForGeeks' in
# '/home / User / Documents'
os.mkdir(path)
print("Directory '%s' created" %directory)

# Directory
directory = "ihritik"

# Parent Directory path
parent_dir = "/home/User/Documents"

# mode
mode = 0o666

# Path
path = os.path.join(parent_dir, directory)

# Create the directory
# 'GeeksForGeeks' in
# '/home / User / Documents'
# with mode 0o666
os.mkdir(path, mode)
print("Directory '%s' created" %directory)
```

**Output:**

```
Directory 'GeeksForGeeks' created
Directory 'ihritik' created

```

**Code #2:** Errors while using os.mkdir() method

```
# Python program to explain os.mkdir() method 

# importing os module 
import os

# Directory
directory = "GeeksForGeeks"

# Parent Directory path
parent_dir = "/home/User/Documents"

# Path
path = os.path.join(parent_dir, directory)

# Create the directory
# 'GeeksForGeeks' in
# '/home / User / Documents'
os.mkdir(path)
print("Directory '%s' created" %directory)

# if directory / file that 
# is to be created already
# exists then 'FileExistsError'
# will be raised by os.mkdir() method

# Similarly, if the specified path
# is invalid 'FileNotFoundError' Error
# will be raised
```

**Output:**

```
Traceback (most recent call last):
  File "osmkdir.py", line 17, in 
    os.mkdir(path)
FileExistsError: [Errno 17] File exists: '/home/User/Documents/GeeksForGeeks'

```

**Code #3:** Handling error while using os.mkdir() method

```
# Python program to explain os.mkdir() method 

# importing os module 
import os

# path
path = '/home/User/Documents/GeeksForGeeks'

# Create the directory
# 'GeeksForGeeks' in
# '/home/User/Documents'
try:
    os.mkdir(path)
except OSError as error:
    print(error)    
```

**Output:**

```
[Errno 17] File exists: '/home/User/Documents/GeeksForGeeks'

```

**参考:**T2】https://docs.python.org/3/library/os.html