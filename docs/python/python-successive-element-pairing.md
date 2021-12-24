# Python–连续元素配对

> 原文:[https://www . geesforgeks . org/python-逐次元素配对/](https://www.geeksforgeeks.org/python-successive-element-pairing/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即每当元素匹配特定条件时，我们都需要用后续元素构造元组。这在日常编程中有潜在的应用。让我们讨论一下执行这项任务的方法。

**方法:使用`zip()` +列表理解**
该任务可以使用上述功能的组合来执行。在这种情况下，zip()执行元组的构造任务，条件匹配和迭代的迎合由列表理解处理。

```
# Python3 code to demonstrate working of
# Successive element pairing
# using zip() + list comprehension

# initialize list
test_list = [1, 4, 'gfg', 7, 8, 'gfg', 9, 'gfg', 10]

# printing original list
print("The original list is : " + str(test_list))

# initialize ele 
ele = 'gfg'

# Successive element pairing
# using zip() + list comprehension
res = [(x, y) for x, y in zip(test_list, test_list[1 : ]) if x == ele]

# printing result
print("Tuple list with desired Successive elements " + str(res))
```

**Output :**

```
The original list is : [1, 4, 'gfg', 7, 8, 'gfg', 9, 'gfg', 10]
Tuple list with desired Successive elements [('gfg', 7), ('gfg', 9), ('gfg', 10)]

```