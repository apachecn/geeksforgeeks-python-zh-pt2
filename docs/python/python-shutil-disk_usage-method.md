# Python | shutil.disk_usage()方法

> 原文:[https://www . geesforgeks . org/python-shutil-disk _ usage-method/](https://www.geeksforgeeks.org/python-shutil-disk_usage-method/)

**Python 中的 Shutil 模块**提供了很多对文件和文件集合进行高级操作的功能。它属于 Python 的标准实用程序模块。该模块有助于文件和目录复制和删除过程的自动化。

`***shutil.disk_usage()***`Python 中的方法是获取关于给定路径的磁盘使用统计。该方法返回一个命名元组，属性为*总计*、*已用*和*自由*。 *total* 属性表示总空间量， *used* 属性表示已用空间量， *free* 属性表示可用空间量，单位为字节。

**注意:**在 Windows 上，给定的路径必须代表一个目录，但在 Unix 系统上，它可以是文件或目录。

> ***语法:***shutil . disk _ 用法(路径)
> 
> ***参数:***
> **路径**:表示文件系统路径的类路径对象。类似路径的对象是表示路径的字符串或字节对象。
> 
> ***返回类型:*** 该方法返回一个命名元组，该元组包含属性化的 total、used 和 free。

**Code:** Use of shutil.disk_usage() method

```py
# Python program to explain shutil.disk_usage() method 

# importing shutil module 
import shutil

# Path
path = "/home/User/Documents"

# Get the disk usage statistics
# about the given path
stat = shutil.disk_usage(path)

# Print disk usage statistics
print("Disk usage statistics:")
print(stat)
```

**Output:**

```py
Disk usage statistics:
usage(total=244934381568, used=13350301696, free=219070689280)

```

**参考:**T2】https://docs.python.org/3/library/shutil.html