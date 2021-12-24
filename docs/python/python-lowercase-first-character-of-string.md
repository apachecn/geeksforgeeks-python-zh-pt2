# Python |字符串的小写第一个字符

> 原文:[https://www . geesforgeks . org/python-小写-字符串第一个字符/](https://www.geeksforgeeks.org/python-lowercase-first-character-of-string/)

字符串大写的问题很常见，已经讨论过很多次了。但是有时候，我们可能会遇到这样的问题，我们需要将字符串的第一个字符转换为小写。让我们讨论一下实现这一点的某些方法。

**方法#1:使用字符串切片+ `lower()`**
这个任务可以很容易地使用较低的方法来执行，该方法降低了提供给它的字符的大小，切片可以用来添加小写第一个字符后的剩余字符串。

```py
# Python3 code to demonstrate working of
# Lowercase first character of String
# Using lower() + string slicing

# initializing string 
test_str = "GeeksforGeeks"

# printing original string 
print("The original string is : " + str(test_str))

# Using lower() + string slicing
# Lowercase first character of String
res = test_str[0].lower() + test_str[1:]

# printing result 
print("The string after lowercasing initial character : " + str(res))
```

**Output :**

```py
The original string is : GeeksforGeeks
The string after lowercasing initial character : geeksforGeeks

```