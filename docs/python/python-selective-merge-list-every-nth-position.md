# Python |每第 n 个位置选择性合并列表

> 原文:[https://www . geesforgeks . org/python-选择性-合并-列表-每 n 个位置/](https://www.geeksforgeeks.org/python-selective-merge-list-every-nth-position/)

有时，在使用 Python 列表时，我们会遇到一个问题，需要在列表中执行合并。简单的列表合并更容易执行。但是有时候，我们需要处理合并中的变化。一个这样的列表可以在每第 n 个元素处将一个列表与另一个列表合并。这个特殊的问题可以在日常编程和竞争性编程中面对。让我们讨论一下执行这项任务的具体方法。

**方法:使用 loop + `extend() + iter() + next()`**
在这个方法中，我们使用蛮力的方法来解决这个问题。在本文中，我们将一个更大的列表转换成一个迭代器，然后使用 next()访问它的元素。这背后的整个想法是更快地获取元素。每 N 个元素检查一个较小的列表。

```py
# Python3 code to demonstrate working of
# Selective Merge list every Nth position
# using loop + extend() + iter() + next()

# initialize lists
test_list1 = [1, 4, 9, 10, 19, 65, 78, 23, 78]
test_list2 = [8, 14, 50]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Selective Merge list every Nth position
# using loop + extend() + iter() + next()
N = 3
temp_iter = iter(test_list1)
res = []
for ele in test_list2:
    res.extend([next(temp_iter) for _ in range(N - 1)])
    res.append(ele)
res.extend(temp_iter)

# printing result
print("The List after merge is : " + str(res))
```

**Output :**

```py
The original list 1 is : [1, 4, 9, 10, 19, 65, 78, 23, 78]
The original list 2 is : [8, 14, 50]
The List after merge is : [1, 4, 8, 9, 10, 14, 19, 65, 50, 78, 23, 78]

```