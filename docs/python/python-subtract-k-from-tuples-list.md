# Python–从元组列表中减去 K

> 原文:[https://www . geesforgeks . org/python-从元组中减去 k-list/](https://www.geeksforgeeks.org/python-subtract-k-from-tuples-list/)

有时，在处理数据时，我们可能会遇到需要对元组执行更新操作的问题。这可以应用于许多领域，例如 web 开发。让我们讨论某些可以进行 K 减的方法。

**方法#1:使用列表理解**
这是可以应用于执行该任务的蛮力函数的简写。在这种情况下，我们对每个元组的每个元素进行迭代，以执行 K 个数据的批量减法。

```
# Python3 code to demonstrate working of
# Subtract K from tuples list
# Using list comprehension

# initialize list
test_list = [(1, 3, 4), (2, 4, 6), (3, 8, 1)]

# printing original list 
print("The original list : " + str(test_list))

# initialize add element
K = 4

# Subtract K from tuples list
# Using list comprehension
res = [tuple(j - K for j in sub ) for sub in test_list]

# printing result
print("List after subtraction of K : " + str(res))
```

**Output :**

```
The original list : [(1, 3, 4), (2, 4, 6), (3, 8, 1)]
List after subtraction of K : [(-3, -1, 0), (-2, 0, 2), (-1, 4, -3)]

```