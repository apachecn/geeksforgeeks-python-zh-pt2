# Python |在字符串中拆分文本和数字

> 原文:[https://www . geesforgeks . org/python-拆分-字符串中的文本和数字/](https://www.geeksforgeeks.org/python-splitting-text-and-number-in-string/)

有时，我们有一个字符串，它由文本和数字组成(反之亦然)，两者之间没有任何特定的区别。可能有一个要求，我们要求将文本与数字分开。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`re.compile() + re.match() + re.groups()`**
上述所有 regex 函数的组合可用于执行该特定任务。在这种情况下，我们编译一个正则表达式，并将其与文本和数字分别组合成一个元组。

```
# Python3 code to demonstrate working of
# Splitting text and number in string 
# Using re.compile() + re.match() + re.groups()
import re

# initializing string 
test_str = "Geeks4321"

# printing original string 
print("The original string is : " + str(test_str))

# Using re.compile() + re.match() + re.groups()
# Splitting text and number in string 
temp = re.compile("([a-zA-Z]+)([0-9]+)")
res = temp.match(test_str).groups()

# printing result 
print("The tuple after the split of string and number : " + str(res))
```

**Output :**

```
The original string is : Geeks4321
The tuple after the split of string and number : ('Geeks', '4321')

```