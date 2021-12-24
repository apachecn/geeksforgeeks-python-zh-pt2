# Python–删除元组

中 K 的第一次出现

> 原文:[https://www . geeksforgeeks . org/python-remove-首次出现元组中的 k/](https://www.geeksforgeeks.org/python-remove-first-occurrence-of-k-in-tuple/)

有时，在使用 Python 元组时，我们可能会遇到一个问题，即我们需要删除元组中元素的第一次出现。这类问题可以应用于许多领域，如学校编程。让我们讨论执行这项任务的某些方法。

> **输入** : test_tuple = (5，6，5，4，7，8，4)，K = 5
> **输出** : (6，5，4，7，8，4)
> 
> **输入** : test_tuple = (5，6，8，4，7，8，4)，K = 8
> **输出** : (5，6，4，7，8，4)

**方法#1:使用`index() + loop + list slicing`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用 index()执行提取 K 的第一次出现的任务，并使用列表切片对元素移除后的元组进行重新排序。

```py
# Python3 code to demonstrate working of 
# Remove first occurrence of K in Tuple
# Using index() + loop + list slicing

# initializing tuples
test_tuple = (5, 6, 4, 4, 7, 8, 4)

# printing original tuple
print("The original tuple : " + str(test_tuple))

# initializing K 
K = 4

# Remove first occurrence of K in Tuple
# Using index() + loop + list slicing
try:
    idx = test_tuple.index(K)
    res = test_tuple[:idx] + test_tuple[idx + 1:]
except ValueError:  
    res = test_tuple

# printing result 
print("Tuple after element removal : " + str(res))
```

**Output :**

```py
The original tuple : (5, 6, 4, 4, 7, 8, 4)
Tuple after element removal : (5, 6, 4, 7, 8, 4)

```

**方法 2:使用`enumerate()` +生成器表达式**
这是可以执行该任务的方式之一。这提供了一个解决这个问题的线性方法。在本文中，我们使用 enumerate()执行检查元素和索引的任务。

```py
# Python3 code to demonstrate working of 
# Remove first occurrence of K in Tuple
# Using enumerate() + generator expression

# initializing tuples
test_tuple = (5, 6, 4, 4, 7, 8, 4)

# printing original tuple
print("The original tuple : " + str(test_tuple))

# initializing K 
K = 4

# Remove first occurrence of K in Tuple
# Using enumerate() + generator expression
res = tuple(ele for idx, ele in enumerate(test_tuple) if idx != test_tuple.index(K))

# printing result 
print("Tuple after element removal : " + str(res))
```

**Output :**

```py
The original tuple : (5, 6, 4, 4, 7, 8, 4)
Tuple after element removal : (5, 6, 4, 7, 8, 4)

```