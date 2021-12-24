# Python |相似值最大键值元组

> 原文:[https://www . geesforgeks . org/python-具有最大相似值键的元组/](https://www.geeksforgeeks.org/python-tuples-with-maximum-key-of-similar-values/)

有时候，在使用 Python 时，我们可能会遇到一个问题，需要获取所有记录。这些数据可以有相似的值，我们需要找到最大键值对。处理数据时可能会出现这种问题。让我们讨论一下完成这项任务的某些方法。

**方法一:使用 `max() + groupby() + itemgetter()` +列表理解**
以上功能的组合可以用来执行这个特定的任务。在这种情况下，我们首先使用`groupby() and itemgetter()`对相似值元素进行分组，然后使用`max()`提取最大值，并使用列表理解在列表中累加结果。

```py
# Python3 code to demonstrate working of
# Tuples with maximum key of similar values
# using max() + groupby() + itemgetter() + list comprehension
from operator import itemgetter
from itertools import groupby

# initialize list
test_list = [(4, 3), (2, 3), (3, 10), (5, 10), (5, 6)]

# printing original list
print("The original list : " + str(test_list))

# Tuples with maximum key of similar values
# using max() + groupby() + itemgetter() + list comprehension
res = [max(values) for key, values in groupby(test_list, key = itemgetter(1))]

# printing result
print("The records retaining maximum keys of similar values : " + str(res))
```

**Output :**

```py
The original list : [(4, 3), (2, 3), (3, 10), (5, 10), (5, 6)]
The records retaining maximum keys of similar values : [(4, 3), (5, 10), (5, 6)]

```