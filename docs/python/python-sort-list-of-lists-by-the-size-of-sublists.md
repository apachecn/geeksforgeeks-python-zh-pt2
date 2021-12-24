# Python |按子列表的大小对列表进行排序

> 原文:[https://www . geesforgeks . org/python-按子列表的大小排序列表/](https://www.geeksforgeeks.org/python-sort-list-of-lists-by-the-size-of-sublists/)

给定一个列表，任务是根据子列表的大小对列表进行排序。让我们讨论几个方法来做同样的事情。

**方法#1:使用排序**

```py
# Python code to demonstrate
# sort list of list
# on the basis of size of sublist

ini_list = [[1, 2, 3], [1, 2], [1, 2, 3, 4],
                [1, 2, 3, 4, 5], [2, 4, 6]]

# printing initial ini_list
print ("initial list", str(ini_list))

# sorting on bais of size of list
ini_list.sort(key = len)

# printing final result
print("final list", str(ini_list))
```

**Output:**

> 初始列表[[1，2，3]，[1，2]，[1，2，3，4]，[1，2，3，4，5]，[2，4，6]]
> 最终列表[[1，2]，[1，2，3]，[2，4，6]，[1，2，3，4]，[1，2，3，4]，[1，2，3，4，5]]