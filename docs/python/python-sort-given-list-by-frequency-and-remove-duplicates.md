# Python |按频率给定列表排序并删除重复项

> 原文:[https://www . geesforgeks . org/python-按频率排序-给定列表-删除重复项/](https://www.geeksforgeeks.org/python-sort-given-list-by-frequency-and-remove-duplicates/)

与重复项的排序和移除相关的问题在开发领域和通用编码中非常常见。已经讨论了按频率排序，但是有时，我们甚至希望删除重复项，而不使用更多的 LOC，并且使用更短的方式。让我们讨论一下实现这一点的某些方法。

**方法#1:使用 count() + set() + sorted()**

排序函数可用于根据需要对元素进行排序，频率可使用计数函数计算，重复项的移除可使用 set 函数处理。

```py
# Python3 code to demonstrate
# sorting and removal of duplicates
# Using sorted() + set() + count()

# initializing list
test_list = [5, 6, 2, 5, 3, 3, 6, 5, 5, 6, 5]

# printing original list
print("The original list : " + str(test_list))

# using sorted() + set() + count()
# sorting and removal of duplicates
res = sorted(set(test_list), key = lambda ele: test_list.count(ele))

# print result
print("The list after sorting and removal : " + str(res))
```

**Output :**

```py
The original list : [5, 6, 2, 5, 3, 3, 6, 5, 5, 6, 5]
The list after sorting and removal : [2, 3, 6, 5]

```

**方法二:使用`Counter.most_common()` +列表理解**

如果有按频率递减排序的特殊用例，也可以使用 Counter 库最常用的函数来获取频率部分。

```py
# Python3 code to demonstrate
# sorting and removal of duplicates
# Using Counter.most_common() + list comprehension
from collections import Counter

# initializing list
test_list = [5, 6, 2, 5, 3, 3, 6, 5, 5, 6, 5]

# printing original list
print("The original list : " + str(test_list))

# using Counter.most_common() + list comprehension
# sorting and removal of duplicates
res = [key for key, value in Counter(test_list).most_common()]

# print result
print("The list after sorting and removal : " + str(res))
```

**Output :**

```py
The original list : [5, 6, 2, 5, 3, 3, 6, 5, 5, 6, 5]
The list after sorting and removal : [5, 6, 3, 2]

```