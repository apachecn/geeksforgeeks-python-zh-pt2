# Python |矩阵中第 n 列垂直字符串

> 原文:[https://www . geesforgeks . org/python-第 n 列-垂直-矩阵中的字符串/](https://www.geeksforgeeks.org/python-nth-column-vertical-string-in-matrix/)

有时，在使用 Python Matrix 时，我们会遇到一个问题，即我们需要以垂直形式访问 Matrix，并从中提取字符串，也可以将其作为字符串，而不仅仅是字符列表。这个任务在游戏中有它的应用，我们需要在填字游戏中提取字符串。让我们讨论一下执行这项任务的方法。

**方法:使用列表理解+ `join()`**
我们分 2 步完成这个方法中的任务。在第一步中，使用列表理解提取第 n 列元素。在第二步中，这些元素结合在一起执行字符到字符串的转换。

```
# Python3 code to demonstrate working of
# Nth Column vertical string in Matrix
# Using join() + list comprehension

# initializing list 
test_list = [('a', 'g', 'v'), ('e', 'f', 8), ('b', 'g', 0)]

# printing list 
print("The original list : " + str(test_list))

# initializing Nth column
N = 1

# Nth Column vertical string in Matrix
# Using join() + list comprehension
temp = [sub[N] for sub in test_list]
res = "".join(temp)

# Printing result
print("Constructed vertical string : " + str(res))
```

**Output :**

```

The original list : [('a', 'g', 'v'), ('e', 'f', 8), ('b', 'g', 0)]
Constructed vertical string : gfg

```