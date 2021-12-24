# Python | os.getenvb()方法

> 原文:[https://www.geeksforgeeks.org/python-os-getenvb-method/](https://www.geeksforgeeks.org/python-os-getenvb-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的`***os.getenvb()***`方法是`***[os.getenv()](https://www.geeksforgeeks.org/python-os-getenv-method/)***`方法的字节版。此方法还返回与指定键关联的环境变量的值。但与`***[os.getenv()](https://www.geeksforgeeks.org/python-os-getenv-method/)***`方法不同，它接受一个 bytes 对象作为关键字，并返回一个 bytes 对象作为与指定关键字相关联的环境变量的值。

只有当环境的本机操作系统类型为字节时，`***os.getenvb()***`方法的功能才可用。例如，Windows 没有字节作为环境的本机操作系统类型，因此`***os.getenvb()***`方法的功能在 Windows 上不可用。

> ***语法:*** os.getenvb(键，默认值=无)
> 
> ***参数:***
> **键:**表示环境变量名称的字节对象
> 默认值(可选) :表示键不存在时的默认值的字符串。如果省略，默认设置为“无”。
> 
> ***返回类型:*** 该方法返回一个 bytes 对象，该对象表示与指定键相关的环境变量的值。如果键不存在，它将返回*默认参数*的值。

**Code #1:** use of os.getenvb() method

```
# Python program to explain os.getenvb() method 

# importing os module 
import os

# Get the value of 'HOME'
# environment variable
key = b'HOME'
value = os.getenvb(key)

# Print the value of 'HOME'
# environment variable
print("Value of 'HOME' environment variable :", value) 

# Get the value of 'JAVA_HOME'
# environment variable
key = b'JAVA_HOME'
value = os.getenvb(key)

# Print the value of 'JAVA_HOME'
# environment variable
print("Value of 'JAVA_HOME' environment variable :", value) 
```

**Output:**

```
Value of 'HOME' environment variable : b'/home/ihritik'
Value of 'JAVA_HOME' environment variable : b'/opt/jdk-10.0.1'

```

**Code #2:** If key does not exist

```
# Python program to explain os.getenvb() method 

# importing os module 
import os

# Get the value of 'home'
# environment variable
key = b'home'
value = os.getenvb(key)

# Print the value of 'home'
# environment variable
print("Value of 'home' environment variable :", value)
```

**Output:**

```
Value of 'home' environment variable : None

```

**Code #3:** Explicitly specifying default parameter

```
# Python program to explain os.getenvb() method 

# importing os module 
import os

# Get the value of 'home'
# environment variable
key = b'home'
value = os.getenvb(key, default = "value does not exist")

# Print the value of 'home'
# environment variable
print("Value of 'home' environment variable :", value) 
```

**Output:**

```
Value of 'home' environment variable : value does not exist

```

**参考:**T2【https://docs . python . org/3/library/OS . html # OS . getenvb()