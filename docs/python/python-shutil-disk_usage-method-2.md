# Python | shutil.disk_usage()方法

> 原文:[https://www . geesforgeks . org/python-shutil-disk _ usage-method-2/](https://www.geeksforgeeks.org/python-shutil-disk_usage-method-2/)

**Python 中的 Shutil 模块**提供了很多对文件和文件集合进行高级操作的功能。它属于 Python 的标准实用程序模块。该模块有助于文件和目录复制和删除过程的自动化。
`shutil.disk_usage()`方法将给定路径的磁盘使用情况统计作为命名元组，属性为**总计**、**已用**和**空闲**，其中**总计**代表内存总量，**已用**代表已用内存，**空闲**代表空闲内存。
**注:**所有内存值以字节为单位。

> **语法:** shutil.disk_usage(路径)
> 
> **参数:**
> **路径:**代表路径的字符串。
> 
> **返回值:**该方法返回一个命名元组，该元组具有属性 total、used 和 free，即总空间、已用空间和可用空间，以字节为单位

**示例#1 :**
使用`shutil.disk_usage()`方法了解 GeeksforGeeks 服务器的内存使用统计。

```
# Python program to explain shutil.disk_usage() method 

# importing os module 
import os 

# importing shutil module 
import shutil 

# path 
# As the path for GFG is root so '/' is used
path = '/'

# Using shutil.disk_usage() method
memory = shutil.disk_usage(path) 

# Print result
print(memory)
```

**Output:**

```
usage(total=51976970240, used=27151167488, free=24809025536)

```

**示例#2 :**
使用`shutil.disk_usage()`方法了解任何用户计算机的内存使用统计。

```
# Python program to explain shutil.disk_usage() method 

# importing os module 
import os 

# importing shutil module 
import shutil 

# path 
path = 'C:/Users/User_name/GeeksforGeeks'

# Using shutil.disk_usage() method
memory = shutil.disk_usage(path) 

# Print result
print(memory)
```

**Output:**

```
usage(total=209190907904, used=92728918016, free=116461989888)

```