# Python |矩阵创建 n*n

> 原文:[https://www.geeksforgeeks.org/python-matrix-creation-of-nn/](https://www.geeksforgeeks.org/python-matrix-creation-of-nn/)

在数据科学中处理数字时，我们经常会遇到这样的问题:我们需要处理数据科学，我们需要将一个数字转换为连续数字的矩阵，因此这个问题有很好的应用。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用列表理解**
通过对需要连续构建的每个列表使用范围函数，可以使用列表理解来完成这个特定的任务。

```
# Python3 code to demonstrate
# matrix creation of n * n
# using list comprehension

# initializing N
N = 4

# printing dimension
print("The dimension : " + str(N))

# using list comprehension
# matrix creation of n * n
res = [list(range(1 + N * i, 1 + N * (i + 1)))
                            for i in range(N)]

# print result
print("The created matrix of N * N: " + str(res))
```

**Output :**

```
The dimension : 4
The created matrix of N*N: [[1, 2, 3, 4], [5, 6, 7, 8], [9, 10, 11, 12], [13, 14, 15, 16]]

```