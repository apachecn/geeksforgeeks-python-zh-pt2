# Python–最大化嵌套元组

> 原文:[https://www . geesforgeks . org/python-maximum-nested-元组/](https://www.geeksforgeeks.org/python-maximize-nested-tuples/)

有时，在处理记录时，我们会遇到一个问题，即我们需要对元组元素执行索引方式的最大化。这可能会变得复杂，因为元组元素是元组，内部元素也是元组。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用 `zip() + max()` +嵌套生成器表达式**
以上功能的组合可以用来执行任务。在本文中，我们使用 zip()组合元组中的元素。迭代和最大化逻辑由生成器表达式提供。

```py
# Python3 code to demonstrate working of
# Maximizing Nested Tuples
# using zip() + nested generator expression + max()

# initialize tuples
test_tup1 = ((1, 3), (4, 5), (2, 9), (1, 10))
test_tup2 = ((6, 7), (3, 9), (1, 1), (7, 3))

# printing original tuples
print("The original tuple 1 : " + str(test_tup1))
print("The original tuple 2 : " + str(test_tup2))

# Maximizing Nested Tuples
# using zip() + nested generator expression + max()
res = tuple(tuple(max(a, b) for a, b in zip(tup1, tup2))\
    for tup1, tup2 in zip(test_tup1, test_tup2))

# printing result
print("The resultant tuple after maximization : " + str(res))
```

**Output :**

```py
The original tuple 1 : ((1, 3), (4, 5), (2, 9), (1, 10))
The original tuple 2 : ((6, 7), (3, 9), (1, 1), (7, 3))
The resultant tuple after maximization : ((6, 7), (4, 9), (2, 9), (7, 10))

```