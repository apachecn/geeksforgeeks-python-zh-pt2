# Python | os.urandom()方法

> 原文:[https://www.geeksforgeeks.org/python-os-urandom-method/](https://www.geeksforgeeks.org/python-os-urandom-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

`os.urandom()`方法用于生成一串适合密码使用的大小随机字节或者我们可以说这个方法生成一个包含随机字符的字符串。

> **语法:** os.urandom(大小)
> 
> **参数:**
> **大小:**是字符串随机字节的大小
> 
> **返回值:**该方法返回一个字符串，该字符串表示适合加密使用的随机字节。

**示例#1 :**

```
# Python program to explain os.urandom() method 

# importing os module 
import os 

# Declaring size
size = 5

# Using os.urandom() method
result = os.urandom(size) 

# Print the random bytes string
# Output will be different everytime
print(result) 
```

**Output:**

```
b'\xe2\xaf\xbc:\xdd'

```