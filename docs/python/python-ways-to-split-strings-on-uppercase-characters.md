# Python |在大写字符上拆分字符串的方法

> 原文:[https://www . geesforgeks . org/python-大写字符拆分字符串的方法/](https://www.geeksforgeeks.org/python-ways-to-split-strings-on-uppercase-characters/)

给定一个字符串，编写一个 Python 程序在大写字符上拆分字符串。让我们讨论几个解决问题的方法。
**方法#1:使用 re.findall()方法**

## 蟒蛇 3

```py
# Python code to demonstrate
# to split strings
# on uppercase letter

import re

# Initialising string
ini_str = 'GeeksForGeeks'

# Printing Initial string
print ("Initial String", ini_str)

# Splitting on UpperCase using re
res_list = []
res_list = re.findall('[A-Z][^A-Z]*', ini_str)

# Printing result
print("Resultant prefix", str(res_list))
```

**Output:** 

```py
Initial String GeeksForGeeks
Resultant prefix ['Geeks', 'For', 'Geeks']

```