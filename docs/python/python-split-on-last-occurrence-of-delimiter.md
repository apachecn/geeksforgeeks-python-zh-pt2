# Python |分隔符最后一次出现时拆分

> 原文:[https://www . geesforgeks . org/python-分隔符最后一次出现时拆分/](https://www.geeksforgeeks.org/python-split-on-last-occurrence-of-delimiter/)

字符串的拆分一直在各种应用程序和用例中讨论。列表拆分的一个有趣的变化是在分隔符上拆分列表，但这次只在最后一次出现时拆分。让我们讨论一下实现这一点的某些方法。

**方法#1:使用 `rsplit(str, 1)`**
正常的字符串拆分可以从前端执行拆分，但是 Python 也提供了另一种方法，可以从后端执行这个任务，因此增加了应用程序的通用性。

```
# Python3 code to demonstrate
# Split on last occurrence of delimiter
# using rsplit()

# initializing string 
test_string = "gfg, is, good, better, and best"

# printing original string 
print("The original string : " + str(test_string))

# using rsplit()
# Split on last occurrence of delimiter
res = test_string.rsplit(', ', 1)

# print result
print("The splitted list at the last comma : " + str(res))
```

**Output :**

```
The original string : gfg, is, good, better, and best
The splitted list at the last comma : ['gfg, is, good, better', 'and best']

```