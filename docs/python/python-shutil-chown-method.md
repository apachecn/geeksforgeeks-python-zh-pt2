# Python | shutil.chown()方法

> 原文:[https://www.geeksforgeeks.org/python-shutil-chown-method/](https://www.geeksforgeeks.org/python-shutil-chown-method/)

**Python 中的 Shutil 模块**提供了很多对文件和文件集合进行高级操作的功能。它属于 Python 的标准实用程序模块。该模块有助于自动处理和删除文件和目录。
***shutil . chown()***Python 中的方法用于更改指定路径的所有者和/或组。

> ***语法:*** shutil.chown(路径，用户=无，组=无)
> ***参数:***
> **路径:**代表有效路径的字符串值。
> **用户:**代表系统用户的字符串值
> **组:**代表组的字符串值
> 用户和组也可以分别由用户 id (uid)和组 id (gid)给出。
> ***返回类型:*** 此方法不返回任何值。

**代码#1:** 使用 ***shutil.chown()*** 方法更改指定路径的所有者和组

## 蟒蛇 3

```
# Python program to explain shutil.chown() method

# importing shutil module
import shutil

# importing Path class of pathlib module
from pathlib import Path

# Path
path = '/home/ihritik/Desktop/file.txt'

# Get the owner and group
# of the specified path
# using Path.owner() and
# Path.group() method
info = Path(path)
user = info.owner()
group = info.group()

# Print owner and group
# of the specified path
print("Current owner and group of the specified path")
print("Owner:", user)
print("Group:", group)

# Now, change the owner and group
# of the specified path
user = 'ihritik'
group = 'ihritik'
shutil.chown(path, user, group)

print("\nOwner and group changed")

# Print the owner and group
# of the specified path
info = Path(path)
user = info.owner()
group = info.group()
print("Current owner:", user)
print("Current group:", group)

# Change only group
# of the specified path
# and let owner as it is
group = 'root'

shutil.chown(path, group = group)

print("\nOnly group changed")

# Print the owner and
# group of the specified path
info = Path(path)
user = info.owner()
group = info.group()
print("Current owner:", user)
print("Current group:", group)

# Similarly, we can change
# only owner of the
# specified path and let
# group as it is
```

**Output:** 

```
Current owner and group of the specified path
Owner: root
Group: root

Owner and group changed
Current owner: ihritik
Current group: ihritik

Only group changed
Current owner: ihritik
Current group: root
```

**代码#2:** 使用 ***shutil.chown()*** 方法

## 蟒蛇 3

```
# Python program to explain shutil.chown() method

# We can also change owner
# and group of the specified path
# by passing owner id (uid) and
# group id (gid) as parameter
# instead of passing name of
# owner and / or group

# importing shutil module
import shutil

# importing Path class of pathlib module
from pathlib import Path

# Path
path = '/home/ihritik/Desktop/file.txt'

# Get the owner user and
# group of the specified path
# using Path.owner() and
# Path.group() method
info = Path(path)
user = info.owner()
group = info.group()
print("Current owner and group of the specified path")
print("Current owner:", user)
print("Current group:", group)

# Now, change the owner user
# and group of the
# specified path

uid = 0
gid = 0
shutil.chown(path, uid, gid)

print("\nOwner and group changed")

# Print the owner user and
# group of the specified path
info = Path(path)
user = info.owner()
group = info.group()
print("Current owner:", user)
print("Current group:", group)
```

**Output:** 

```
Current owner and group of the specified path
Owner: ihritik
Group: ihritik

Owner and group changed
Current owner: root
Current group: root
```

**参考:**T2https://docs.python.org/3/library/shutil.html