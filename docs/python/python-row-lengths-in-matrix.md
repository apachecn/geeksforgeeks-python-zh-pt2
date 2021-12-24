# Python |矩阵中的行长度

> 原文:[https://www.geeksforgeeks.org/python-row-lengths-in-matrix/](https://www.geeksforgeeks.org/python-row-lengths-in-matrix/)

矩阵问题在竞争程序设计和数据科学领域都很常见。我们可能面临的一个这样的问题是在大小不均匀的矩阵中寻找矩阵行的长度。让我们讨论一下解决这个问题的某些方法。

**方法一:使用`max() + map() + sum()` +列表理解**

上述函数的组合有助于在一行中获得这个特定问题的解决方案，因此非常有用。sum 函数计算子列表的和，max 函数可用于降序排序，所有这些都使用列表理解绑定在一起。

```
# Python3 code to demonstrate
# Row lengths in matrix
# using max() + map() + sum() + list comprehension

# initializing list
test_list = [[4, 5, 6], [7, 8], [2]]

# printing original list
print("The original list : " + str(test_list))

# using max() + map() + sum() + list comprehension
# Row lengths in matrix
res = [sum(len(row) > idx for row in test_list)
    for idx in range(max(map(len, test_list)))]

# print result
print("The row lengths in matrix : " + str(res))
```

**Output :**

```
The original list : [[4, 5, 6], [7, 8], [2]]
The row lengths in matrix : [3, 2, 1]

```

**方法 2:使用`sum() + filter() + zip_longest()`**

这个问题也可以用上面的一组函数来解决。过滤函数可用于获取单独的列表，求和函数完成的求和绑定任务由 zip _ longest 函数执行。

```
# Python3 code to demonstrate
# Row lengths in matrix
# using sum() + filter() + zip_longest()
from itertools import zip_longest

# initializing list
test_list = [[4, 5, 6], [7, 8], [2]]

# printing original list
print("The original list : " + str(test_list))

# using sum() + filter() + zip_longest()
# Row lengths in matrix
res = [sum(1 for idx in filter(None.__ne__, i))
              for i in zip_longest(*test_list)]

# print result
print("The row lengths in matrix : " + str(res))
```

**Output :**

```
The original list : [[4, 5, 6], [7, 8], [2]]
The row lengths in matrix : [3, 2, 1]

```