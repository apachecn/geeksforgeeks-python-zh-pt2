# Python |字符串中给定字符的最长运行时间

> 原文:[https://www . geesforgeks . org/python-给定字符串的最长运行时间/](https://www.geeksforgeeks.org/python-longest-run-of-given-character-in-string/)

有时，在处理字符串时，我们会遇到一个问题，需要提取某个字母的最长连续的长度。这可以在 web 开发和竞争性编程中得到应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是我们可以执行这个任务的蛮力方法。在这种情况下，我们在字符串上运行一个循环，并在每次运行时继续记忆最大值。

```py
# Python3 code to demonstrate working of 
# Longest Run of Character in String
# Using loop

# initializing string
test_str = 'geeksforgeeeks'

# printing original string
print("The original string is : " + test_str)

# initializing K 
K = 'e'

# Longest Run of Character in String
# Using loop
res = 0
cnt = 0
for chr in test_str:
    if chr == K:
        cnt += 1
    else:
        res = max(res, cnt)
        cnt = 0
res = max(res, cnt)

# printing result 
print("Longest Run length of K : " + str(res)) 
```

**Output :**

```py
The original string is : geeksforgeeeks
Longest Run length of K : 3

```

 **方法 2:使用`max() + re.findall()`**
这是解决这个问题的一种线性方式。在本例中，我们使用 findall()找到了所有运行的最大值。

```py
# Python3 code to demonstrate working of 
# Longest Run of Character in String
# Using max() + re.findall()
import re

# initializing string
test_str = 'geeksforgeeeks'

# printing original string
print("The original string is : " + test_str)

# initializing K 
K = 'e'

# Longest Run of Character in String
# Using max() + re.findall()
res = len(max(re.findall(K + '+', test_str), key = len))

# printing result 
print("Longest Run length of K : " + str(res)) 
```

**Output :**

```py
The original string is : geeksforgeeeks
Longest Run length of K : 3

```