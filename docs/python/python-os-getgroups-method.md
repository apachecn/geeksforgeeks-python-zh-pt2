# Python | os.getgroups()方法

> 原文:[https://www.geeksforgeeks.org/python-os-getgroups-method/](https://www.geeksforgeeks.org/python-os-getgroups-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

os 模块中的所有函数在文件名和路径无效或不可访问的情况下都会引发 **OSError** ，或者其他具有正确类型但不被操作系统接受的参数。

`***os.getgroups()***`Python 中的方法用于获取与当前进程关联的补充组 id 列表。

**补充组 id**:在 Unix 系统中，每个用户必须是至少一个称为主组的组的成员。用户也有可能在组数据库的相关条目中被列为其他组的成员。这些附加组的标识称为补充组标识

**注意:** `***os.getgroups()***`方法仅在 UNIX 系统上可用。

> ***语法:***os.getgroups()
> 
> ***参数:*** 不需要参数
> 
> ***返回类型:*** 此方法返回一个列表，该列表表示与当前进程关联的补充组 id

**代码:**使用 OS . getgroups()方法

```py
# Python program to explain os.getgroups() method 

# importing os module 
import os

# Get the list of supplementary
# group IDs associated with
# the current process
s_grp_id = os.getgroups()

# Print the list
print("Supplementary group IDs associated with the current process:")
print(s_grp_id)
```

T30