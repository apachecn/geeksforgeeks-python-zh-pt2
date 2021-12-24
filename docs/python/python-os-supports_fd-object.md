# Python | os.supports_fd 对象

> 原文:[https://www.geeksforgeeks.org/python-os-supports_fd-object/](https://www.geeksforgeeks.org/python-os-supports_fd-object/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

*操作系统模块*中的一些方法允许将路径参数指定为打开文件描述符(fd)。由于不同的平台提供不同的功能，fd 参数可能在一个平台上受支持，但在另一个平台上不受支持。Python 中的`***os.supports_fd***`方法是一个 set 对象，它指示*操作系统模块*中的哪些方法允许将它们的路径参数指定为打开的文件描述符。

特定方法是否允许将其路径参数指定为打开文件描述符，可以使用`***os.supports_fd***` 上的操作符中的*进行检查。
**例如:**
下面的表达式检查 [os.stat()](https://www.geeksforgeeks.org/python-os-stat-method/) 方法是否允许在本地平台上调用时将其路径参数指定为打开的文件描述符。*

```
os.stat in os.supports_fd

```

> ***语法:*** os.supports_fd
> 
> ***参数:*** 这是一个不可调用的集合对象。因此，不需要任何参数。
> 
> ***返回类型:*** 该方法返回一个 set 对象，该对象代表*操作系统模块*中的方法，该模块允许将它们的路径参数指定为打开文件描述符。

**Code #1:** Use of os.supports_fd object

```
# Python program to explain os.supports_fd object  

# importing os module 
import os

# Get the list of all methods
# which permits specifying
# their path parameter as 
# an open file descriptor.
methodList = os.supports_fd

# Print the list
print(methodList)
```

**Output:**

```
{<built-in function execve>, <built-in function stat>, <built-in function truncate>,
<built-in function statvfs>, <built-in function chown>, <built-in function listdir>,
<built-in function chmod>, <built-in function utime>, <built-in function pathconf>,
<built-in function chdir>}

```

**Code #2:** Use of os.supports_fd object to check if a particular method permits specifying their path parameter as an open file descriptor or not.

```
# Python program to explain os.supports_fd object  

# importing os module 
import os

# Check whether os.stat() method
# permits specifying their path parameter
# as an open file descriptor or not
support = os.stat in os.supports_fd

# Print result
print(support)

# Check whether os.remove() method
# permits specifying their path parameter
# as an open file descriptor or not
support = os.remove in os.supports_fd

# Print result
print(support)
```

**Output:**

```
True
False

```