# Python 字符串| zill()

> 原文:[https://www.geeksforgeeks.org/python-string-zfill/](https://www.geeksforgeeks.org/python-string-zfill/)

**zfill()** 方法返回给定字符串左侧填充有“0”字符的字符串副本。

**语法:**

```py
str.zfill(length)

```

**参数:**

> **length :** length 是从 zfill()返回的字符串的长度，左边填充“0”位。

**返回:**

```py
Returns a copy of the string with '0' characters   
padded to the leftside of the given string.

```

**代码 1**

```py
text = "geeks for geeks"

print(text.zfill(25))

print(text.zfill(20))

# Given length is less than
# the length od original string
print(text.zfill(10))
```

输出:

```py
0000000000geeks for geeks
00000geeks for geeks
geeks for geeks

```

**代码 2**

```py
number = "6041"
print(number.zfill(8))

number = "+6041"
print(number.zfill(8))

text = "--anything%(&%(%)*^"
print(text.zfill(20))
```

输出:

```py
00006041
+0006041
-0-anything%(&%(%)*^

```