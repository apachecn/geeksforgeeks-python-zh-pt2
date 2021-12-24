# Python | OS . supports _ follow _ symlink 对象

> 原文:[https://www . geesforgeks . org/python-OS-supports _ follow _ symlinks-object/](https://www.geeksforgeeks.org/python-os-supports_follow_symlinks-object/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

*操作系统模块*中的一些方法允许使用它们的*follow _ symlink*参数。由于不同的平台提供不同的功能，*follow _ symlink*参数可能在一个平台上受支持，但在另一个平台上不受支持。Python 中的`***os.supports_follow_symlinks***`是一个设置对象，它指示*操作系统模块*中的哪些方法允许使用它们的 *follow_symlinks* 参数

特定方法是否允许使用其*follow _ symlink*参数，可以使用`***os.supports_follow_symlinks***` 上的操作符中的*进行检查。
**例如:**
下面的表达式检查 [os.stat()](https://www.geeksforgeeks.org/python-os-stat-method/) 方法在本地平台上调用时是否允许使用其*follow _ symlink*参数。*

```
os.stat in os.supports_follow_symlinks

```

> ***语法:***OS . supports _ follow _ symlink
> 
> ***参数:*** 这是一个不可调用的集合对象。因此，不需要任何参数。
> 
> ***返回类型:*** 该方法返回一个 set 对象，该对象代表*操作系统模块*中的方法，该模块允许使用它们的 follow _ symlinks 参数。

**Code #1:** Use of os.supports_follow_symlinks object

```
# Python program to explain os.supports_follow_symlinks object  

# importing os module 
import os

# Get the list of all methods
# which permits the use of their
# follow_symlinks parameter
methodList = os.supports_follow_symlinks

# Print the list
print(methodList)
```

**Output:**

```
{<built-in function stat>, <built-in function chown>,
<built-in function link>, <built-in function access>, 
<built-in function utime>}

```

**Code #2:** Use of os.supports_follow_symlinks object to check if a particular method permits the use of their follow_symlinks parameter or not.

```
# Python program to explain os.supports_follow_symlinks object  

# importing os module 
import os

# Check whether os.stat() method
# permits the use of their 
# follow_symlinks parameter or not
support = os.stat in os.supports_follow_symlinks

# Print result
print(support)

# Check whether os.fwalk() method
# permits the use of their
# follow_symlinks parameter or not
support = os.fwalk in os.supports_follow_symlinks

# Print result
print(support)
```

**Output:**

```
True
False

```