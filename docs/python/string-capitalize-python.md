# Python 中的字符串大写()

> 原文:[https://www.geeksforgeeks.org/string-capitalize-python/](https://www.geeksforgeeks.org/string-capitalize-python/)

在 Python 中，**大写()**方法返回原始字符串的副本，并将字符串的第一个字符转换为大写**(大写)**字母，同时将字符串中的所有其他字符**变为小写**字母。

**语法:**

```py
*string_name*.capitalize() 

string_name: It is the name of string of
             whose first character we want
             to capitalize.
```

**参数:**大写()函数不取任何参数。
**返回值:**大写()函数返回以大写为第一个字符的字符串。
下面是 python 程序来说明大写()函数:

## 计算机编程语言

```py
# Python program to demonstrate the
# use of capitalize() function

# capitalize() first letter of string
# and make other letters lowercase
name = "geeks FOR geeks"

print(name.capitalize())

# demonstration of individual words
# capitalization to generate camel case
name1 = "geeks"
name2 = "for"
name3 = "geeks"
print(name1.capitalize() + name2.capitalize()
                         + name3.capitalize())
```

**输出:**

```py
Geeks for geeks
GeeksForGeeks
```