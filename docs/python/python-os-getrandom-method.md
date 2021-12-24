# Python | os.getrandom()方法

> 原文:[https://www.geeksforgeeks.org/python-os-getrandom-method/](https://www.geeksforgeeks.org/python-os-getrandom-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

`os.getrandom()`方法用于生成一串适合密码使用的大小随机字节或者我们可以说这个方法生成一个包含随机字符的字符串。它还可以用来播种用户空间随机数生成器。它返回的字节数可能比请求的少。

> **语法** os.getrandom(大小，标志)
> 
> **参数:**
> **大小:**是字符串随机字节的大小
> **标志:**是一个位掩码，可以包含零个或多个标志或在一起。旗帜是操作系统。GRND_RANDOM 和 GRND_NONBLOCK。
> 
> **返回值:**该方法返回一个字符串，该字符串表示适合加密使用的随机字节。

**旗帜–**

> **os。GRND_NONBLOCK:** 如果设置了此标志，那么 getrandom()不会阻塞，而是在没有随机字节可供读取时立即引发 BlockingIOError。
> 
> **os。GRND_RANDOM:** 如果该位被置位，则从/dev/random 池中抽取随机字节。

**示例#1 :**

```py
# Python program to explain os.getrandom() method 

# importing os module 
import os 

# Declaring size
size = 5

# Using os.getrandom() method
# Using os.GRND_NONBLOCK flag
result = os.getrandom(size, os.GRND_NONBLOCK) 

# Print the random bytes string
# Output will be different everytime
print(result) 
```

**Output:**

```py
b'5\n\xe0\x98\x15'

```

**例 2 :**

```py
# Python program to explain os.getrandom() method 

# importing os module 
import os 

# Declaring size
size = 5

# Using os.getrandom() method
# Using os.GRND_RANDOM flag
result = os.getrandom(size, os.GRND_RANDOM) 

# Print the random bytes string
# Output will be different everytime
print(result) 
```

**Output:**

```py
b'\xce\xc8\xf3\x95%'

```