# Python |上半部分之间的子串频率

> 原文:[https://www . geesforgeks . org/python-substring-frequency-inter-upper ses/](https://www.geeksforgeeks.org/python-substring-frequency-between-uppercases/)

有时在处理字符串时，我们会遇到一个问题，那就是我们必须找到出现在上半部分之间的子字符串，并找到它们的频率。这是一个非常独特的问题，应用较少。让我们讨论执行这项任务的某些方法。

**方法#1:使用`groupby()` + regex + loop**
以上功能的组合可以用来执行这个任务。在本文中，我们使用 groupby()对正则表达式提取的子字符串进行分组。所有的都是用循环编译的。

```
# Python3 code to demonstrate working of 
# Substring Frequency between Uppercases
# Using groupby() + regex + loop
from itertools import groupby
import re

# initializing string
test_str = "GeEkSForGeEkS"

# printing original string
print("The original string is : " + test_str)

# Substring Frequency between Uppercases
# Using groupby() + regex + loop
res = {}
for i, j in groupby(re.findall(r'[A-Z][a-z]*\d*', test_str)):
    res[i] = res[i] + 1 if i in res.keys() else 1 

# printing result 
print("The grouped Substring Frequency : " + str(res)) 
```

**Output :**

```
The original string is : GeEkSForGeEkS
The grouped Substring Frequency : {'For': 1, 'S': 2, 'Ek': 2, 'Ge': 2}

```