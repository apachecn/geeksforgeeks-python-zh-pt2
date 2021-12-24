# Python | os.supports_dir_fd 对象

> 原文:[https://www . geesforgeks . org/python-OS-supports _ dir _ FD-object/](https://www.geeksforgeeks.org/python-os-supports_dir_fd-object/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

操作系统模块中的一些方法采用了一个 *dir_fd* 参数。由于不同的平台提供不同的功能，dir_fd 参数可能在一个平台上可用，但在另一个平台上不可用。Python 中的`***os.supports_dir_fd***`方法是一个集合对象，它指示*操作系统模块*中的哪些方法允许使用它们的 dir_fd 参数。

要检查特定方法是否允许使用其 *dir_fd* 参数，可以使用`***os.supports_dir_fd***` 上的操作符中的*进行检查。
**例如:**
下面的表达式检查 [os.stat()](https://www.geeksforgeeks.org/python-os-stat-method/) 方法的 *dir_fd* 参数在本地是否可用*

```py
os.stat in os.supports_dir_fd

```

> ***语法:*** os.supports_dir_fd
> 
> ***参数:*** 这是一个不可调用的集合对象。因此，不需要任何参数。
> 
> ***返回类型:*** 该方法返回一个 set 对象，该对象代表*操作系统模块*中的方法，该模块允许使用它们的 dir_fd 参数。

**Code #1:** Use of os.supports_dir_fd object to get the list of methods which permits the use of their dir_fd parameter

```py
# Python program to explain os.supports_dir_fd object  

# importing os module 
import os

# Get the list of all methods
# who permits the use of
# their dir_fd parameter
methodList = os.supports_dir_fd

# Print the list
print(methodList)
```

**Output:**

```py
{<built-in function symlink>, <built-in function stat>, <built-in function chown>,
<built-in function link>, <built-in function readlink>, <built-in function access>,
<built-in function rename>, <built-in function chmod>, <built-in function utime>,
<built-in function mknod>, <built-in function unlink>, <built-in function mkdir>,
<built-in function mkfifo>, <built-in function rmdir>, <built-in function open>}

```

**Code #2:** Use of os.supports_dir_fd object to check if a particular method permits the use of its dir_fd parameter or not

```py
# Python program to explain os.supports_dir_fd object  

# importing os module 
import os

# Check whether os.stat() method
# permits the use of its dir_fd
# parameter or not
support = os.stat in os.supports_dir_fd

# Print result
print(support)

# Check whether os.lstat() method
# permits the use of its dir_fd
# parameter or not
support = os.lstat in os.supports_dir_fd

# Print result
print(support)
```

**Output:**

```py
True
False

```