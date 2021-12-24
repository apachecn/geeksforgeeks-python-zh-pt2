# Python |根据键

移除连续元组

> 原文:[https://www . geesforgeks . org/python-remove-continuous-tuple-照键/](https://www.geeksforgeeks.org/python-remove-consecutive-tuple-according-to-key/)

有时，在使用 Python 列表时，我们可能会遇到这样的问题:我们可能有一个元组列表，我们希望将它们从元组的第一个元素中移除，以避免它的连续重复。让我们讨论一下解决这个问题的某些方法。

**方法:使用`groupby() + itemgetter() + next()`**
该任务可以使用这些功能的组合来执行。在这种情况下，我们使用`next()`将列表转换为迭代器，以便更快地访问，`itemgetter()`用于获取我们需要对其执行删除的元组的索引(在这种情况下是第一个)，而`groupby()`执行元素的最终分组。

```
# Python3 code to demonstrate working of
# Remove Consecutive tuple according to key
# using itemgetter() + next() + groupby()
from operator import itemgetter
from itertools import groupby

# initialize list
test_list = [(4, 5), (4, 6), (7, 8), (7, 1), (7, 0), (8, 1)]

# printing original list
print("The original list is : " + str(test_list))

# Remove Consecutive tuple according to key
# using itemgetter() + next() + groupby()
res = [next(group) for key, group in groupby(test_list, key = itemgetter(0))]

# printing result
print("List after Consecutive tuple removal : " + str(res))
```

**Output :**

```
The original list is : [(4, 5), (4, 6), (7, 8), (7, 1), (7, 0), (8, 1)]
List after Consecutive tuple removal : [(4, 5), (7, 8), (8, 1)]

```