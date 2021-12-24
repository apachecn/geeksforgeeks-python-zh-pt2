# Python |字符串中的范围复制

> 原文:[https://www . geesforgeks . org/python-range-in-string 重复/](https://www.geeksforgeeks.org/python-range-duplication-in-string/)

有时，在处理字符串时，我们会遇到一个问题，即我们需要在范围内连续复制字符串的范围。这种问题在日常编程领域会有应用。让我们讨论执行这项任务的特定方式。

**方法:使用字符串切片**
这是直接解决这个问题的方法。在这种情况下，我们执行切割要重复的字符串并附加其副本的任务。前切片和后切片分别附加到其前缀和后缀，以构建结果字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Range duplication in String
# Using string slicing

# initializing string
test_str = "geeksforgeeks"

# printing original string
print("The original string is : " + test_str)

# initializing range 
i, j = 3, 6

# Range duplication in String
# Using string slicing
temp = test_str[i:j] * 2 
res = test_str[:i] + temp + test_str[j:]

# printing result 
print("The string after range duplication : " + res) 
```

**Output :**

```
The original string is : geeksforgeeks
The string after range duplication : geeksfksforgeeks

```