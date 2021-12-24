# Python | os.lchown()方法

> 原文:[https://www.geeksforgeeks.org/python-os-lchown-method/](https://www.geeksforgeeks.org/python-os-lchown-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

os 模块中的所有函数在文件名和路径无效或不可访问的情况下都会引发 **OSError** ，或者其他具有正确类型但不被操作系统接受的参数。

Python 中的`***os.lchown()***`方法用于将指定文件路径的*所有者*和*组 id* 更改为指定的数字*所有者 id* (UID)和*组 id* (GID)。该方法不遵循符号链接，相当于`***os.chown(path, uid, gid, follow_symlinks = False)***`方法。

**注意:** `***os.lchown()***`方法仅在 UNIX 平台上可用，该方法的功能通常只对超级用户或特权用户可用。

> ***语法:***OS . lctown(PTH，uid，gid)
> 
> ***参数:***
> **路径**:表示要设置所有权的文件路径的类路径对象。
> **uid** :代表要为文件设置的所有者 id 的整数值。
> **gid** :代表要为文件设置的组 id 的整数值。
> 
> ***返回类型:*** 此方法不返回值。

**Code #1:** Use of os.lchown() method

```py
# Python program to explain os.lchown() method 

# importing os module 
import os

# File path
path = "./file.txt"

# Print the current owner id
# and group id of the file

# os.stat() method will return a 
# 'stat_result’ object of
# ‘os.stat_result’ class whose
# 'st_uid' and 'st_gid' attributes
# will represent owner id and group id
# of the file respectively 
print("Owner id of the file:", os.stat(path).st_uid)
print("Group id of the file:", os.stat(path).st_gid) 

# Change the owner id and 
# the group id of the file
# using os.lchown() method
uid = 400
gid = 500
os.lchown(path, uid, gid)
print("\nOwner and group id of the file changed")

# Print the owner id
# and group id of the file
print("\nOwner id of the file:", os.stat(path).st_uid)
print("Group id of the file:", os.stat(path).st_gid) 
```

**输出:**
![os.lchown() mwthod terminal output](img/bc995b01bef15b953107dde61662be8b.png)

**Code #2:** Use of os.lchown() method to set any one id and leave other unchanged.

```py
# Python program to explain os.lchown() method 

# importing os module 
import os

# File path
path = "./file.txt"

# Print the current owner id
# and group id of the file

# os.stat() method will return a 
# 'stat_result’ object of
# ‘os.stat_result’ class whose
# 'st_uid' and 'st_gid' attributes
# will represent owner id and group id
# of the file respectively 
print("Owner id of the file:", os.stat(path).st_uid)
print("Group id of the file:", os.stat(path).st_gid) 

# Change only group id of 
# the file and leave 
# owner id unchanged

# set id as -1 to leave
# it unchanged
uid = 1000
gid = -1
os.lchown(path, uid, gid)
print("\ngroup id of the file changed")

# Print the owner id
# and group id of the file
print("\nOwner id of the file:", os.stat(path).st_uid)
print("Group id of the file:", os.stat(path).st_gid) 
```

**输出:**
![os.lchown() method terminal output](img/0750841325c99ef35aff81f5bc827384.png)

**Code #3:** If the specified path is a symlink

```py
# Python program to explain os.lchown() method 

# importing os module 
import os

# File path
path = "./file.txt"

# Creating a symlink
# of the above path  
# using os.symlink() method
symlink = "file(symlink).txt"
os.symlink(path, symlink)

# Print the current owner id
# and group id of the file
# as well as the symlink pointing
# to the above specified file path 
print("Owner id of the file:", os.stat(path).st_uid)
print("Group id of the file:", os.stat(path).st_gid) 

print("Owner id of the symlink:", os.stat(symlink).st_uid)
print("Group id of the symlink:", os.stat(symlink).st_gid) 

# Change the ownership 
# of the symlink pointing 
# to the above file 'file.txt'
uid = 600
gid = 700
os.lchown(symlink, uid, gid)
print("\nOwner id and group id changed")

# Print the owner id
# and group id of the file
# as well as the symlink pointing
# to the above specified file path
print("\nOwner id of the file:", os.stat(path).st_uid)
print("Group id of the file:", os.stat(path).st_gid) 

print("Owner id of the symlink:", os.stat(symlink).st_uid)
print("Group id of the symlink:", os.stat(symlink).st_gid)

# As os.lchown() method
# does not follow symlinks
# so, we can not change the
# owner and group id 
# through a symlink 
```

**输出:**
![os.lchown() method terminal output](img/d0ed3cbc903404d9a8b25887b2dc25b3.png)

**参考:**T2】https://docs.python.org/3/library/os.html