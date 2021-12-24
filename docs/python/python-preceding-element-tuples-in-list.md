# Python |列表中的前置元素元组

> 原文:[https://www . geesforgeks . org/python-before-element-tuples-in-list/](https://www.geeksforgeeks.org/python-preceding-element-tuples-in-list/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即每当前面的元素与特定条件匹配时，我们都需要用该元素构造元组。这在日常编程中有潜在的应用。让我们讨论一下执行这项任务的方法。

**方法:使用`zip()` +列表理解**
该任务可以使用上述功能的组合来执行。其中`zip()`执行元组构建任务，条件匹配和迭代的迎合由列表理解处理。
 **代码:**

```py
# Python3 code to demonstrate working of
# Preceding Tuple elements in list
# using zip() + list comprehension

# initialize list
test_list = [1, 4, 'gfg', 7, 8, 'gfg', 9, 'gfg']

# printing original list
print("The original list is : " + str(test_list))

# initialize ele 
ele = 'gfg'

# Preceding Tuple elements in list
# using zip() + list comprehension
res = [(x, y) for x, y in zip(test_list, test_list[1 : ]) if y == ele]

# printing result
print("Tuple list with desired Preceding elements " + str(res))
```

**Output :**

```py
The original list is : [1, 4, 'gfg', 7, 8, 'gfg', 9, 'gfg']
Tuple list with desired Preceding elements [(4, 'gfg'), (8, 'gfg'), (9, 'gfg')]

```