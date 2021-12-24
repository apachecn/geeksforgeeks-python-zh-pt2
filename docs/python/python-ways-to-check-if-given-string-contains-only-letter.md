# Python |检查给定字符串是否只包含字母的方法

> 原文:[https://www . geesforgeks . org/python-检查给定字符串是否只包含字母的方法/](https://www.geeksforgeeks.org/python-ways-to-check-if-given-string-contains-only-letter/)

给定一个字符串，编写一个 Python 程序来查找一个字符串是否只包含字母而不包含其他关键字。让我们讨论几个完成任务的方法。

**方法#1:使用 isalpha()方法**

## 蟒蛇 3

```
# Python code to demonstrate
# to find whether string contains
# only letters

# Initialising string
ini_str = "ababababa"

# Printing initial string
print ("Initial String", ini_str)

# Code to check whether string contains only number
if ini_str.isalpha():
    print("String contains only letters")
else:
    print("String doesn't contains only letters")
```

**方法 2:使用 re**

## 蟒蛇 3

```
# Python code to demonstrate
# to find whether string contains
# only letters
import re

# Initialising string
ini_str = "ababababa"

# Printing initial string
print ("Initial String", ini_str)

# Code to check whether string contains only number
pattern = re.compile("^[a-zA-Z]+{content}quot;)
if pattern.match(ini_str):
    print ("Contains only letters")
else:
    print ("Doesn't contains only letters")
```