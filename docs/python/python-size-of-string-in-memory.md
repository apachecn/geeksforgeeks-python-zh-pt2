# Python |内存中字符串的大小

> 原文:[https://www . geesforgeks . org/python-内存中字符串大小/](https://www.geeksforgeeks.org/python-size-of-string-in-memory/)

在处理字符串时，有时，我们需要获取字符串的大小，即长度。但是在某些情况下，我们需要获取字符串的字节大小，这在处理文件时通常很有用。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`len() + encode()`**

想到的最简单和初始的方法是将字符串转换成字节格式，然后提取其大小。

```py
# Python3 code to demonstrate
# getting size of string in bytes
# using encode() + len()

# initializing string 
test_string = "geekforgeeks"

# printing original string 
print("The original string : " + str(test_string))

# using encode() + len()
# getting size of string in bytes
res = len(test_string.encode('utf-8'))

# print result
print("The length of string in bytes : " + str(res))
```

**Output :**

```py
The original string : geekforgeeks
The length of string in bytes : 12

```

**方法 2:使用`sys.getsizeof()`**

这个任务也可以通过一个系统调用来执行，由 Python 提供，就像在 sys 函数库中一样，`getsizeof` 函数可以得到我们想要的字符串的字节大小。

```py
# Python3 code to demonstrate
# getting size of string in bytes
# using sys.getsizeof()
import sys

# initializing string 
test_string = "geekforgeeks"

# printing original string 
print("The original string : " + str(test_string))

# using sys.getsizeof()
# getting size of string in bytes
res = sys.getsizeof(test_string)

# print result
print("The length of string in bytes : " + str(res))
```

**Output :**

```py
The original string : geekforgeeks
The length of string in bytes : 12

```