# Python |从嵌套列表中删除重复项

> 原文:[https://www . geesforgeks . org/python-remove-duplicates-from-nested-list/](https://www.geeksforgeeks.org/python-remove-duplicates-from-nested-list/)

在最近的过去，删除重复项的任务发生了很多次，但是有时当我们处理复杂的数据结构时，在这些情况下，我们需要不同的技术来处理这种类型的问题。让我们讨论一下完成这项任务的某些方法。

**方法#1:使用`sorted() + set()`**
这个特殊的问题可以使用上面的函数来解决。这里的想法是对子列表进行排序，然后使用集合操作移除相似的元素，集合操作移除重复的元素。

```py
# Python3 code to demonstrate
# removing duplicate sublist 
# using set() + sorted()

# initializing list
test_list = [[1, 0, -1], [-1, 0, 1], [-1, 0, 1],
                           [1, 2, 3], [3, 4, 1]]

# printing original list
print("The original list : " + str(test_list))

# using set() + sorted()
# removing duplicate sublist
res = list(set(tuple(sorted(sub)) for sub in test_list))

# print result
print("The list after duplicate removal : " + str(res))  
```

**Output :**

```py
The original list : [[1, 0, -1], [-1, 0, 1], [-1, 0, 1], [1, 2, 3], [3, 4, 1]]
The list after duplicate removal : [(-1, 0, 1), (1, 3, 4), (1, 2, 3)]

```