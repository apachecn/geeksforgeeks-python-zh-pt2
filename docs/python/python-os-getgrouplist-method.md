# Python | os.getgrouplist()方法

> 原文:[https://www . geesforgeks . org/python-OS-getgroup list-method/](https://www.geeksforgeeks.org/python-os-getgrouplist-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

os 模块中的所有函数在文件名和路径无效或不可访问的情况下都会引发 **OSError** ，或者其他具有正确类型但不被操作系统接受的参数。

在类似 UNIX 的系统中，可以将多个用户放入一个组。一个*组标识符*，通常缩写为 *GID* ，是一个用于表示特定组的数值。它将一个系统用户与共享某些共同之处的其他用户关联起来。

`***os.getgrouplist()***`Python 中的方法用于获取指定用户所属的所有组 id 的列表。

**注意:** `***os.getgrouplist()***`方法只在 UNIX 平台上可用。

> ***语法:*** os.getgrouplist(用户，gid)
> 
> ***参数:***
> **用户**:代表系统用户的字符串值。
> **gid** :表示组 id 的整数值。
> 如果 gid 不属于指定用户，也将包含在返回列表中
> 
> ***返回类型:*** 该方法返回一个列表，该列表代表指定用户所属的所有组 id。

**Code:** Use of os.getgrouplist() method

```py
# Python program to explain os.getgrouplist() method 

# importing os module 
import os

# System user
user = "ihritik"

# Group id
gid = 100

# Get the list of all
# group ids the specified user
# belongs to using
# os.getgrouplist() method
groupList = os.getgrouplist(user, gid)

# Print the list
print("% s is associated with the following group ids:" % user)
print(groupList, "\n")

# System user
user = "root"

# Group id
gid = 100

# Get the list of all
# group ids the specified user
# belongs to using
# os.getgrouplist() method
groupList = os.getgrouplist(user, gid)

# Print the list
print("%s is associated with the following group ids:" %user)
print(groupList)

# If the specified gid does not
# belongs to the specified user
# it will also be included in 
# the list of groups
```

**Output:**

```py
ihritik is associated with the following group ids:
[100, 4, 24, 27, 30, 46, 118, 128] 

root is associated with the following group ids:
[100]

```

![os.getgrouplist() method output](img/56104d244af906e9516ef26fae828b21.png)