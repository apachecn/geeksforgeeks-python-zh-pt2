# Python |用 K 替换标点符号

> 原文:[https://www . geesforgeks . org/python-replace-标点符号-with-k/](https://www.geeksforgeeks.org/python-replace-punctuations-with-k/)

有时，在使用 Python 字符串时，我们会遇到一个问题，需要用特定的字符替换字符串中的标点符号。这可以应用于许多领域，如日常编程。让我们讨论执行这项任务的某些方法。

**方法#1:使用`string.punctuation + replace()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用标点符号提取所有标点符号，并使用 replace()执行所需字符的替换。

```
# Python3 code to demonstrate working of 
# Replace punctuations with K
# Using string.punctuation + replace()
from string import punctuation

# initializing string
test_str = 'geeksforgeeks, is : best for ; geeks !!'

# printing original string
print("The original string is : " + str(test_str))

# initializing replace character
repl_char = '*'

# Replace punctuations with K
# Using string.punctuation + replace()
for chr in punctuation:
    test_str = test_str.replace(chr, repl_char)

# printing result 
print("The strings after replacement : " + test_str) 
```

**Output :**

```
The original string is : geeksforgeeks, is : best for ; geeks!!
The strings after replacement : geeksforgeeks* is * best for * geeks**

```