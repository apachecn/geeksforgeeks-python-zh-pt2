# Python |统计字符串中子串个数的方法

> 原文:[https://www . geesforgeks . org/python-计数方式-字符串中的子字符串数量/](https://www.geeksforgeeks.org/python-ways-to-count-number-of-substring-in-string/)

给定一个字符串和一个子字符串，编写一个 Python 程序来查找字符串中有多少数量的子字符串(包括重叠的情况)。下面我们来讨论几个方法。

**方法一:使用`re.findall()`**

```
# Python code to demonstrate 
# to count total number
# of substring in string

import re
# Initialising string
ini_str = "ababababa"
sub_str = 'aba'

# Count count of substrings using re.findall
res = len(re.findall('(?= aba)', ini_str))

# Printing result
print("Number of substrings", res)
```

**输出:**

```
Number of substrings 0

```