# Python |合并列表的重叠部分

> 原文:[https://www . geesforgeks . org/python-merge-重叠-列表的一部分/](https://www.geeksforgeeks.org/python-merge-overlapping-part-of-lists/)

有时候，在使用 Python 列表时，我们会遇到一个问题，那就是我们必须合并两个列表的重叠部分。这种问题会出现在日常编程领域。让我们讨论一下解决这个问题的方法。

**方法:使用生成器+ `next()` +列表切片**
这个方法可以用来解决这个任务。在这种情况下，首先，我们从一个列表的后端迭代一个变量，并获得第一个列表后端的切片，直到第二个列表的初始切片匹配。然后，我们使用`next()`获得第一个这样的重叠(最大重叠)，然后使用列表切片加入剩余部分。

```
# Python3 code to demonstrate working of
# Merge overlapping parts of list
# using generator + next() + list slicing

# initialize lists
test_list1 = [4, 5, 7, 9, 10, 11]
test_list2 = [10, 11, 16, 17]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Merge overlapping parts of list
# using generator + next() + list slicing
temp = (i for i in range(len(test_list2), 0, -1) if test_list2[:i] == test_list1[-i:])
temp2 = next(temp, 0)
res = test_list1 + test_list2[temp2 : ]

# printing result
print("List after overlapping merge is : " + str(res))
```

**Output :**

```
The original list 1 is : [4, 5, 7, 9, 10, 11]
The original list 2 is : [10, 11, 16, 17]
List after overlapping merge is : [4, 5, 7, 9, 10, 11, 16, 17]

```