# Python |矩阵中的相对排序顺序

> 原文:[https://www . geesforgeks . org/python-相对-排序-矩阵中的顺序/](https://www.geeksforgeeks.org/python-relative-sorted-order-in-matrix/)

有时，在使用 Python Matrix 时，我们可以让数据随机排列，并且我们可以有一个要求，即我们需要按照 Matrix 的排序顺序获取元素位置。让我们讨论一下执行这项任务的特定方式。

**方法:使用列表理解+ `enumerate() + sort() + lambda`**
结合以上功能可以实现问题的解决。在这些中，我们需要首先使用 `enumerate()`和列表理解来排列用于索引值元组创建的元素。然后，我们使用 sort 函数使用 lambda 函数执行自定义排序。
 **代码:**

```py
# Python3 code to demonstrate working of
# Relative sorted order in Matrix
# using list comprehension + enumerate() + sort() + lambda

# initialize list
test_list = [[1, 3, 1], [4, 6], [7, 8, 10]]

# printing original list
print("The original list is : " + str(test_list))

# Relative sorted order in Matrix
# using list comprehension + enumerate() + sort() + lambda
res = [(i, j) for i, x in enumerate(test_list) for
       j, _ in enumerate(x)]
res.sort(key = lambda f: test_list[f[0]][f[1]])

# printing result
print("Sorted order of Matrix elements : " + str(res))
```

**Output :**

```py
The original list is : [[1, 3, 1], [4, 6], [7, 8, 10]]
Sorted order of Matrix elements : [(0, 0), (0, 2), (0, 1), (1, 0),
                                   (1, 1), (2, 0), (2, 1), (2, 2)]

```