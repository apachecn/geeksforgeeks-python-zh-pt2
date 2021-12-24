# Python |从字符串中移除子字符串列表

> 原文:[https://www . geesforgeks . org/python-remove-substring-list-from-string/](https://www.geeksforgeeks.org/python-remove-substring-list-from-string/)

有时，在使用 Python 字符串时，我们可能会遇到需要从字符串中移除子字符串的问题。这个相当容易，以前解决过很多次。但有时，我们会处理需要删除的字符串列表，并相应地调整字符串。让我们讨论完成这项任务的某些方法。

**方法#1:使用 loop + `replace()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 replace()执行多个字符串的替换。

```
# Python3 code to demonstrate working of 
# Remove substring list from String
# Using loop + replace()

# initializing string
test_str = "gfg is best for all geeks"

# printing original string
print("The original string is : " + test_str)

# initializing sub list 
sub_list = ["best", "all"]

# Remove substring list from String
# Using loop + replace()
for sub in sub_list:
    test_str = test_str.replace(' ' + sub + ' ', ' ')

# printing result 
print("The string after substring removal : " + test_str) 
```

**Output :**

```
The original string is : gfg is best for all geeks
The string after substring removal : gfg is for geeks

```