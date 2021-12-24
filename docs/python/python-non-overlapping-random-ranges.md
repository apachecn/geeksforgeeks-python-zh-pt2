# Python–非重叠随机范围

> 原文:[https://www . geesforgeks . org/python-非重叠-随机-范围/](https://www.geeksforgeeks.org/python-non-overlapping-random-ranges/)

有时，在使用 Python 时，我们可能会遇到这样的问题，即我们需要提取 N 个随机范围，这些范围本质上是不重叠的，并且具有给定的范围大小。这可能有我们处理数据的应用程序。让我们讨论执行这项任务的特定方式。

**方法:使用`any() + randint()` +循环**
这是可以执行这个任务的蛮力方式。在本文中，我们使用 randint()提取随机范围，并使用 any()和 loop 检查数字范围是否不重复。

```
# Python3 code to demonstrate working of 
# Non-overlapping Random Ranges
# Using loop + any() + randint()
import random

# initializing N 
N = 7

# initializing K 
K = 5

# Non-overlapping Random Ranges
# Using loop + any() + randint()
tot = 10000
res = set()
for _ in range(N):
  temp = random.randint(0, tot - K) 
  while any(temp >= idx and temp <= idx + K for idx in res):
     temp = random.randint(0, tot - K) 
  res.add(temp)
res = [(idx, idx + K) for idx in res]

# printing result 
print("The N Non-overlapping Random ranges are : " + str(res)) 
```

**Output :**

```
The N Non-overlapping Random ranges are : [(5347, 5352), (7108, 7113), (5479, 5484), (1906, 1911), (2228, 2233), (5206, 5211), (3260, 3265)]

```