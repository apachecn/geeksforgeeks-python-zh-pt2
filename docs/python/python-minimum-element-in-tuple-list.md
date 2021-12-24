# Python |元组列表中的最小元素

> 原文:[https://www . geesforgeks . org/python-元组列表中的最小元素/](https://www.geeksforgeeks.org/python-minimum-element-in-tuple-list/)

有时，在处理记录形式的数据时，我们可能会遇到一个问题，即我们需要找到收到的所有记录的最小元素。这是数据科学领域中非常常见的应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`min()` +生成器表达式**

这是实现解决这一任务的最基本方法。在这种情况下，我们使用生成器表达式迭代整个嵌套列表，并使用`min()`获得最小元素。

```py
# Python3 code to demonstrate working of
# Minimum element in tuple list
# using min() + generator expression

# initialize list 
test_list = [(2, 4), (6, 7), (5, 1), (6, 10), (8, 7)]

# printing original list 
print("The original list : " + str(test_list))

# Minimum element in tuple list
# using min() + generator expression
res = min(int(j) for i in test_list for j in i)

# printing result
print("The Minimum element of list is : " + str(res))
```

**Output :**

```py
The original list : [(2, 4), (6, 7), (5, 1), (6, 10), (8, 7)]
The Minimum element of list is : 1

```

**方法 2:使用`min() + map() + chain.from_iterable()`**

上述方法的组合也可用于执行该任务。在这种情况下，求最小值的扩展是通过组合 `map() and from_iterable()`来完成的。

```py
# Python3 code to demonstrate working of
# Minimum element in tuple list
# using min() + map() + chain.from_iterable()
from itertools import chain

# initialize list 
test_list = [(2, 4), (6, 7), (5, 1), (6, 10), (8, 7)]

# printing original list 
print("The original list : " + str(test_list))

# Minimum element in tuple list
# using min() + map() + chain.from_iterable()
res = min(map(int, chain.from_iterable(test_list)))

# printing result
print("The Minimum element of list is : " + str(res))
```

**Output :**

```py
The original list : [(2, 4), (6, 7), (5, 1), (6, 10), (8, 7)]
The Minimum element of list is : 1

```