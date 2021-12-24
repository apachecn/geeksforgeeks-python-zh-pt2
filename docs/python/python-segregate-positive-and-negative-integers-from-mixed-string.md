# Python |从混合字符串中分离正负整数

> 原文:[https://www . geesforgeks . org/python-从混合字符串中分离正负整数/](https://www.geeksforgeeks.org/python-segregate-positive-and-negative-integers-from-mixed-string/)

有时，在处理 Python 字符串数据时，我们可能会遇到一个问题，即需要将字符串中的正整数和负整数分开。这可能发生在包括数据处理在内的许多领域。让我们讨论一下解决这个问题的某些方法。

**方法:使用正则表达式**
这个问题可以通过使用合适的正则表达式来解决。在这种情况下，我们将匹配的正则表达式与字符串匹配，并将正整数和负整数从字符串中分离出来。

```py
# Python3 code to demonstrate working of 
# Segregate Positive and Negative Integers
# Using regex
import re

# initializing string
test_str = "gfg + 4-1is + 5best-8"

# printing original string
print("The original string is : " + test_str)

# Segregate Positive and Negative Integers
# Using regex
res = re.findall('[-+]?\d+', test_str)

# printing result 
print("The split string is : " + str(res)) 
```

**Output :**

```py
The original string is : gfg+4-1is+5best-8
The split string is : ['+4', '-1', '+5', '-8']

```