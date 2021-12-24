# Python |后置流浪字符串拆分

> 原文:[https://www . geesforgeks . org/python-后置-杂散-字符串-拆分/](https://www.geeksforgeeks.org/python-rear-stray-character-string-split/)

有时，在使用 Python 字符串时，我们可能会遇到需要拆分字符串的问题。但是有时候，我们可以有这样一种情况，我们在列表的后端分割出一个空格之后。这通常是不可取的。让我们讨论一下避免这种情况的方法。

**方法#1:使用`split() + rstrip()`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们在 split()之前从字符串中移除杂散字符，以避免在 split 列表中出现空字符串。

```
# Python3 code to demonstrate working of 
# Rear stray character String split
# Using split() + rstrip()

# initializing string
test_str = 'gfg, is, best, '

# printing original string
print("The original string is : " + test_str)

# Rear stray character String split
# Using split() + rstrip()
res = test_str.rstrip(', ').split(', ')

# printing result 
print("The evaluated result is : " + str(res)) 
```

**Output :**

```
The original string is : gfg, is, best,
The evaluated result is : ['gfg', 'is', 'best']

```