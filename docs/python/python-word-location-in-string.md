# Python |字符串中的单词位置

> 原文:[https://www . geesforgeks . org/python-word-location-in-string/](https://www.geeksforgeeks.org/python-word-location-in-string/)

有时，在使用 Python 字符串时，我们可能会遇到需要找到特定单词位置的问题。这可以应用于日常编程等领域。让我们讨论完成这项任务的某些方法。

**方法一:使用`re.findall() + index()`**
这是我们可以找到单词存在的位置的方法之一。在本文中，我们使用 findall()查找子字符串模式，并使用 index()查找其位置。

```py
# Python3 code to demonstrate working of 
# Word location in String
# Using findall() + index()
import re

# initializing string
test_str = 'geeksforgeeks is best for geeks'

# printing original string
print("The original string is : " + test_str)

# initializing word 
wrd = 'best'

# Word location in String
# Using findall() + index()
test_str = test_str.split()
res = -1
for idx in test_str:
    if len(re.findall(wrd, idx)) > 0:
        res = test_str.index(idx) + 1

# printing result 
print("The location of word is : " + str(res)) 
```

**Output :**

```py
The original string is : geeksforgeeks is best for geeks
The location of word is : 3

```