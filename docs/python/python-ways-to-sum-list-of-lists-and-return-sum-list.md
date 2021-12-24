# Python |列表求和和返回求和列表的方法

> 原文:[https://www . geeksforgeeks . org/python-to-way-to-sum-list-of-list-and-return-sum-list/](https://www.geeksforgeeks.org/python-ways-to-sum-list-of-lists-and-return-sum-list/)

列表是一个重要的容器，几乎用于日常编程和网络开发的每一个代码中，使用越多，就越需要掌握它，因此对其操作的了解是必要的。给定一个列表，程序假定返回总和作为最终列表。

让我们来看看列表和返回列表相加的一些方法。

**方法# 1:** 使用朴素方法

```py
# Python code to demonstrate
# sum of list of list
# using naive method

# Declaring initial list of list
L = [[1, 2, 3],
     [4, 5, 6],
     [7, 8, 9]]

# Printing list of list
print("Initial List - ", str(L))

# Using naive method
res = list()
for j in range(0, len(L[0])):
    tmp = 0
    for i in range(0, len(L)):
        tmp = tmp + L[i][j]
    res.append(tmp)

# printing result
print("final list - ", str(res))
```

**Output:**

```py
Initial List -  [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
final list -  [12, 15, 18]

```

**方法 2:** 使用 numpy 数组
[一个 numpy](https://www.geeksforgeeks.org/numpy-in-python-set-1-introduction/) 是一个通用数组处理包。它提供了一个高性能的多维数组对象，以及使用这些数组的工具。

```py
# Python code to demonstrate
# sum of list of list
# using numpy array functions
import numpy as np

# Declaring initial list of list
List = np.array([[1, 2, 3],
                 [4, 5, 6],
                 [7, 8, 9]])

# Printing list of list
print("Initial List - ", str(List))

# Using numpy sum
res = np.sum(List, 0)

# printing result
print("final list - ", str(res))
```

**Output:**

```py
Initial List -  [[1 2 3]
                 [4 5 6]
                 [7 8 9]]
final list -  [12 15 18]

```

**方法 3:** 使用`zip()`和列表理解

```py
# Python code to demonstrate
# sum of list of list using 
# zip and list comprehension

# Declaring initial list of list
List = [[1, 2, 3],
        [4, 5, 6],
        [7, 8, 9]]

# Printing list of list
print("Initial List - ", str(List))

# Using list comprehension
res = [sum(i) for i in zip(*List)]

# printing result
print("final list - ", str(res))
```

**Output:**

```py
Initial List -  [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
final list -  [12, 15, 18]

```