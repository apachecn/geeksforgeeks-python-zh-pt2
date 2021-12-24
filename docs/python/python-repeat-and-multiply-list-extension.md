# Python |重复和乘法列表扩展

> 原文:[https://www . geesforgeks . org/python-repeat-and-multiple-list-extension/](https://www.geeksforgeeks.org/python-repeat-and-multiply-list-extension/)

有时，在使用 Python 列表时，我们会遇到一个问题，即我们需要以非常定制的方式扩展列表。我们可能不得不重复列表的内容，在这样做的时候，每次新列表必须是原始列表的倍数。这种增量式扩展在许多领域都有应用。让我们讨论一下执行这项任务的方法。

**方法:使用列表理解**
这个任务可以用蛮力的方式来完成，但是使用列表理解实现的时间越短越好。在这种情况下，我们分两步执行任务，首先我们制作一个帮助列表来形成一个乘法因子列表，然后使用原始列表累积结果。

```py
# Python3 code to demonstrate working of
# Repeat and Multiply list extension
# Using list comprehension

# initializing list
test_list = [4, 5, 6]

# printing original list
print("The original list is : " + str(test_list))

# Extension factor
N = 4

# Multiply factor 
M = 3

# Repeat and Multiply list extension
# Using list comprehension
temp = [1 * M**i for i in range(N)]
res = list([ele * tele for tele in temp for ele in test_list])

# printing result 
print("List after extension and multiplication : " + str(res))
```

**Output :**

```py
The original list is : [4, 5, 6]
List after extension and multiplication : [4, 5, 6, 12, 15, 18, 36, 45, 54, 108, 135, 162]

```