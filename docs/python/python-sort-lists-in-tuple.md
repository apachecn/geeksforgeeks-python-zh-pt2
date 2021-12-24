# Python |元组中的排序列表

> 原文:[https://www.geeksforgeeks.org/python-sort-lists-in-tuple/](https://www.geeksforgeeks.org/python-sort-lists-in-tuple/)

有时，在使用 Python 元组时，我们会遇到一个问题，即我们需要对构成列表的元组进行排序，并且我们需要对每个元组进行排序。让我们讨论执行这项任务的某些方法。

**方法#1:使用`tuple() + sorted()` +生成器表达式**
该任务可以使用上述功能的组合来执行。在本文中，我们使用生成器表达式遍历每个列表，并使用`sorted()`执行排序操作。

```
# Python3 code to demonstrate working of
# Sort lists in tuple
# Using tuple() + sorted() + generator expression

# Initializing tuple
test_tup = ([7, 5, 4], [8, 2, 4], [0, 7, 5])

# printing original tuple
print("The original tuple is : " + str(test_tup))

# Sort lists in tuple
# Using tuple() + sorted() + generator expression
res = tuple((sorted(sub) for sub in test_tup))

# printing result
print("The tuple after sorting lists : " + str(res))
```

**Output :**

```
The original tuple is : ([7, 5, 4], [8, 2, 4], [0, 7, 5])
The tuple after sorting lists : ([4, 5, 7], [2, 4, 8], [0, 5, 7])

```