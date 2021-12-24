# Python |列表中唯一的对

> 原文:[https://www.geeksforgeeks.org/python-unique-pairs-in-list/](https://www.geeksforgeeks.org/python-unique-pairs-in-list/)

有时，在使用 python 列表时，我们可以有一个二进制矩阵(包含 2 个元素的嵌套列表)。我们会遇到一个问题，我们需要找到一对的唯一性。无论顺序如何，一对都是唯一的，它不会再次出现在列表中。让我们讨论一下执行这项任务的具体方法。

**方法:使用`frozenset() + Counter()` +列表理解**
以上功能的组合可以执行此任务。`frozenset()`用于忽略排序，`Counter()`用于执行检查唯一性的任务，迭代使用列表理解完成。

```py
# Python3 code to demonstrate working of
# Unique pairs in list
# using frozenset() + Counter() + list comprehension
from collections import Counter

# initialize list
test_list = [[5, 6], [9, 8], [8, 9], [1, 4], [6, 5], [10, 1]]

# printing original list
print("The original list is : " + str(test_list))

# Unique pairs in list
# using frozenset() + Counter() + list comprehension
temp = Counter(frozenset(ele) for ele in test_list)
res = [temp[frozenset(ele)] == 1 for ele in test_list]

# printing result
print("The Unique status of elements is " + str(res))
```

**Output :**

```py
The original list is : [[5, 6], [9, 8], [8, 9], [1, 4], [6, 5], [10, 1]]
The Unique status of elements is [False, False, False, True, False, True]

```