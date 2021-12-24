# Python–最大连续子串出现次数

> 原文:[https://www . geesforgeks . org/python-最大-连续-子串-出现次数/](https://www.geeksforgeeks.org/python-maximum-consecutive-substring-occurrence/)

有时，在使用 python 时，我们会遇到一个问题，需要检查连续重复中出现的子字符串。这可以在数据域中得到应用。让我们讨论一下执行这项任务的方法。

**方法:使用`max() + re.findall()`**
以上方法的组合可以用来执行此任务。在本文中，我们使用 findall()提取重复的子字符串，并使用 max()提取它们的最大值。

```py
# Python3 code to demonstrate working of 
# Maximum Consecutive Substring  Occurrence
# Using max() + re.findall()
import re

# initializing string
test_str = 'geeksgeeks are geeks for all geeksgeeksgeeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing subs 
sub_str = 'geeks'

# Maximum Consecutive Substring  Occurrence
# Using max() + re.findall()
res = max(re.findall('((?:' + re.escape(sub_str) + ')*)', test_str), key = len)

# printing result 
print("The maximum run of Substring : " + res) 
```

**Output :**

```py
The original string is : geeksgeeks are geeks for all geeksgeeksgeeks
The maximum run of Substring : geeksgeeksgeeks

```