# Python |字符串中的元音索引

> 原文:[https://www . geesforgeks . org/python-元音-索引-in-string/](https://www.geeksforgeeks.org/python-vowel-indices-in-string/)

有时，在使用 Python Strings 时，我们可能会遇到一个问题，需要提取其中元音的索引。这种应用程序在日常编程中很常见。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是执行该任务的一种方式。在这种情况下，我们使用蛮力来执行这项任务。在本文中，我们迭代每个字符串元素并测试元音。

```
# Python3 code to demonstrate working of 
# Vowel indices in String
# Using loop

# initializing string
test_str = "geeksforgeeks"

# printing original string
print("The original string is : " + test_str)

# Vowel indices in String
# Using loop
res = []
for ele in range(len(test_str)):
    if test_str[ele] in "aeiou":
       res.append(ele)

# printing result 
print("The vowel indices are : " + str(res)) 
```

**Output :**

```
The original string is : geeksforgeeks
The vowel indices are : [1, 2, 6, 9, 10]

```