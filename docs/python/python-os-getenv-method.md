# Python | os.getenv()方法

> 原文:[https://www.geeksforgeeks.org/python-os-getenv-method/](https://www.geeksforgeeks.org/python-os-getenv-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的`***os.getenv()***`方法返回环境变量键的值(如果存在的话),否则返回默认值。

> ***语法:*** os.getenv(键，默认值=无)
> 
> ***参数:***
> **键:**表示环境变量名称的字符串
> 默认值(可选) :表示键值不存在时的默认值的字符串。如果省略，默认设置为“无”。
> 
> ***返回类型:*** 这个方法返回一个表示环境变量键值的字符串。如果键不存在，它将返回*默认参数*的值。

**代码#1:** 使用 os.getenv()方法

```
# Python program to explain os.getenv() method 

# importing os module 
import os

# Get the value of 'HOME'
# environment variable
key = 'HOME'
value = os.getenv(key)

# Print the value of 'HOME'
# environment variable
print("Value of 'HOME' environment variable :", value) 

# Get the value of 'JAVA_HOME'
# environment variable
key = 'JAVA_HOME'
value = os.getenv(key)

# Print the value of 'JAVA_HOME'
# environment variable
print("Value of 'JAVA_HOME' environment variable :", value) 
```

**Output:**

```
Value of 'HOME' environment variable : /home/ihritik
Value of 'JAVA_HOME' environment variable : /opt/jdk-10.0.1

```

**代码#2:** 如果密钥不存在

```
# Python program to explain os.getenv() method 

# importing os module 
import os

# Get the value of 'home'
# environment variable
key = 'home'
value = os.getenv(key)

# Print the value of 'home'
# environment variable
print("Value of 'home' environment variable :", value)
```

**Output:**

```
Value of 'home' environment variable : None

```

**代码#3:** 明确指定默认参数

```
# Python program to explain os.getenv() method 

# importing os module 
import os

# Get the value of 'home'
# environment variable
key = 'home'
value = os.getenv(key, "value does not exist")

# Print the value of 'home'
# environment variable
print("Value of 'home' environment variable :", value) 
```

**Output:**

```
Value of 'home' environment variable : value does not exist

```