# Python |移除不一致列表

> 原文:[https://www . geeksforgeeks . org/python-remove-unidenial-list/](https://www.geeksforgeeks.org/python-remove-unidentical-lists/)

有时，在使用 python 列表时，我们可以有一个二进制矩阵(包含 2 个元素的嵌套列表)。我们可能会遇到一个问题，那就是我们需要删除不合理的列表。无论顺序如何，一对都是唯一的，它不会再次出现在列表中。让我们讨论一下执行这项任务的具体方法。

**方法:使用`frozenset() + Counter()` +列表理解**
以上功能的组合可以执行此任务。frozenset()用于忽略排序，Counter()用于执行检查唯一性的任务，迭代使用列表理解完成。

```
# Python3 code to demonstrate working of
# Remove unidentical lists
# using frozenset() + Counter() + list comprehension
from collections import Counter

# initialize list
test_list = [[5, 6], [9, 8], [8, 9], [1, 4], [6, 5], [10, 1]]

# printing original list
print("The original list is : " + str(test_list))

# Remove unidentical lists
# using frozenset() + Counter() + list comprehension
temp = Counter(frozenset(ele) for ele in test_list)
res = [ele for ele in test_list if temp[frozenset(ele)] >= 2]

# printing result
print("The list after removal of unidentical lists : " + str(res))
```

**Output :**

```
The original list is : [[5, 6], [9, 8], [8, 9], [1, 4], [6, 5], [10, 1]]
The list after removal of unidentical lists : [[5, 6], [9, 8], [8, 9], [6, 5]]

```