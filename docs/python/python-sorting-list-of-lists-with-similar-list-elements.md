# Python |对列表元素相似的列表进行排序

> 原文:[https://www . geesforgeks . org/python-排序-列表列表-具有相似列表元素/](https://www.geeksforgeeks.org/python-sorting-list-of-lists-with-similar-list-elements/)

排序一直是许多应用程序执行的关键操作，也是许多问题的子问题。已经讨论了许多变化和技术，它的知识在编程时会很有用。本文讨论包含列表的列表的排序。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`sorted()` +列表理解**
在这个方法中，我们只是对可以应用的较长过程使用速记。该列表被迭代，随后的子列表也使用排序函数对内部列表进行排序。

```py
# Python3 code to demonstrate
# Sorting list of lists with similar list elements
# using list comprehension + sorted()

# initializing list
test_list = [[[4, 4], [1, 1]], [[3, 3], [2, 2], [5, 5]]]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + sorted()
# Sorting list of lists with similar list elements
res = [sorted(idx) for idx in test_list]

# print result
print("The list after performing sort operation : " + str(res))
```

**Output :**

> 原始列表:[[[4，4]，[1，1]]，[[3，3]，[2，2]，[5，5]]]
> 执行排序操作后的列表:[[[1，1]，[4，4]]，[[2，2]，[3，3]，[5，5]]]