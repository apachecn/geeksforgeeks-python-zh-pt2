# Python | os.strerror()方法

> 原文:[https://www.geeksforgeeks.org/python-os-strerror-method/](https://www.geeksforgeeks.org/python-os-strerror-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

os 模块中的所有函数在文件名和路径无效或不可访问的情况下都会引发 **OSError** ，或者其他具有正确类型但不被操作系统接受的参数。

Python 中的`***os.strerror()***`方法用于获取*错误代码*对应的*错误*消息。

> ***语法:***OS . streerror(代码)
> 
> ***参数:***
> **代码**:表示错误代码的整数值
> 
> ***返回类型:*** 该方法返回一个字符串，代表与指定的*错误代码*对应的错误信息。

**Code #1:** Use of os.strerror() method

```py
# Python program to explain os.strerror() method 

# importing os module 
import os

# Get the error message 
# corresponding to 
# error code 1
code = 1
error = os.strerror(code)

# Print the error message 
# corresponding to 
# error code 1
print("Error message corresponding to error code % d:" % code, error)

# Get the error message 
# corresponding to 
# error code 5
code = 5
error = os.strerror(code)

# Print the error message 
# corresponding to 
# error code 5
print("Error message corresponding to error code % d:" % code, error)
```

**Output:**

```py
Error message corresponding to error code 1: Operation not permitted
Error Message corresponding to error code 5: Input/output error

```

**代码#2:** 打印前 20 个错误

```py
# Python program to explain os.strerror() method 

# importing os module 
import os

# Get the error message 
# corresponding to the
# first 20 error codes
n = 20

for i in range(1, n + 1)
    error = os.strerror(code)
    print("Error code % d:" % i, error)
```

**Output:**

```py
Error code 1: Operation not permitted
Error code 2: No such file or directory
Error code 3: No such process
Error code 4: Interrupted system call
Error code 5: Input/output error
Error code 6: No such device or address
Error code 7: Argument list too long
Error code 8: Exec format error
Error code 9: Bad file descriptor
Error code 10: No child processes
Error code 11: Resource temporarily unavailable
Error code 12: Cannot allocate memory
Error code 13: Permission denied
Error code 14: Bad address
Error code 15: Block device required
Error code 16: Device or resource busy
Error code 17: File exists
Error code 18: Invalid cross-device link
Error code 19: No such device
Error code 20: Not a directory

```

**代码#3:** 检查错误消息中的无效错误代码

```py
# Python program to explain os.strerror() method 

# importing os module 
import os

# Get the error message 
# corresponding to 
# error code 200
code = 200
error = os.strerror(code)

# Print the error message 
# corresponding to 
# error code 200
print("Error message corresponding to error code % d:" % code, error)

# Get the error message 
# corresponding to 
# error code 300
code = 300
error = os.strerror(code)

# Print the error message 
# corresponding to 
# error code 300
print("Error message corresponding to error code % d:" % code, error)

# os.strerror() will return
# An unknown error
# in case specified code
# is invalid
```

**Output:**

```py
Error message corresponding to error code 200: Unknown error 200
Error message corresponding to error code 300: Unknown error 300

```