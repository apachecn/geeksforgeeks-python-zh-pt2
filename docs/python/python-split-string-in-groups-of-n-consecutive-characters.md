# Python |将字符串拆分成 n 个连续字符的组

> 原文:[https://www . geesforgeks . org/python-n 个连续字符组中的拆分字符串/](https://www.geeksforgeeks.org/python-split-string-in-groups-of-n-consecutive-characters/)

给定一个字符串(无论是数字字符串还是字符字符串)，编写一个 Python 程序，按照每个 *n 个<sup>第</sup>T3 个*字符拆分该字符串。

**示例:**

```py
Input : str = "Geeksforgeeks", n = 3
Output : ['Gee', 'ksf', 'oor', 'gee', 'ks']

Input : str = "1234567891234567", n = 4
Output : [1234, 5678, 9123, 4567]
```

**方法一:使用列表理解**

```py
# Python code to split string
# by every 3rd number

# String initialization
string = "Geeksforgeeks"

# Defining splitting point
n = 3

# Using list comprehension
out = [(string[i:i+n]) for i in range(0, len(string), n)]

# Printing output
print(out)
```

**Output:**

```py
['Gee', 'ksf', 'org', 'eek', 's']

```

**方法 2:使用`zip_longest`**

```py
# Python code to split string of number
# and character into every 4th number

# Importing
from itertools import zip_longest

# Group function using zip_longest to split
def group(n, iterable, fillvalue=None):
    args = [iter(iterable)] * n
    return zip_longest(fillvalue=fillvalue, *args)

# String initialization
str = '123GeeksForGeeks4567'

# Split point
n=4

# list of separated string
out_string = [''.join(lis) for lis in group(n, str, '')]

# Output list initialization
out_no = []

# Converting list of string into list of integer
for a in out_string:
    out_no.append(a)

# Printing list
print(out_no)
```

**Output:**

```py
['123G', 'eeks', 'ForG', 'eeks', '4567']

```