# Python–OS . replace()方法

> 原文:[https://www.geeksforgeeks.org/python-os-replace-method/](https://www.geeksforgeeks.org/python-os-replace-method/)

**先决条件:**[Python 中的 OS 模块。](https://www.geeksforgeeks.org/os-module-python-examples/)

**Python 中的 os.replace()** 方法用于重命名文件或目录。如果目的地是一个目录，则会出现**错误**。如果目标存在并且是一个文件，如果执行操作的用户有权限，它将被替换而不会出错。如果源和目标位于不同的文件系统上，此方法可能会失败。

> **语法:** os.replace(源，目标，* src _ dir _ FD =无，dst _ dir _ fd =无 2)
> 
> **参数:**
> 
> *   **来源:**我们要重命名的文件或目录的名称。
> *   **目的地:**我们要在目的地中给出的名称。
> *   **src_dir_id :** 此参数存储源目录的或文件，
>     文件描述符指的是一个目录。
> *   **dst_dir_fd:** 是指目录、
>     和操作路径的文件描述符。它应该是相对的，
>     路径将是相对于该目录的。如果
>     路径是绝对的，则忽略 dir_fd。
> 
> **返回类型:**此方法不返回值。

**代码#1** :使用 os.replace()方法重命名文件。

## 蟒蛇 3

```
# Python program to explain os.replace() method

# importing os module
import os

# file name
file = "f.txt"

# File location which to rename
location = "d.txt"

# Path
path = os.replace(file, location)

# renamed the file f.txt to d.txt
print("File %s is renamed successfully" % file)
```

**输出:**

```
File f.txt is renamed successfully
```

**代码#2** :处理可能出现的错误。(如果给出了必要的权限，那么输出将如下所示)

## 计算机编程语言

```
# Python program to explain os.replace() method

# importing os module
import os

# Source file path
source = './file.txt'

# destination file path
dest = './da'

# try renaming the source path
# to destination path
# using os.rename() method

try:
    os.replace(source, dest)
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
```

**输出:**

```
Source is a file but destination is a directory.
```