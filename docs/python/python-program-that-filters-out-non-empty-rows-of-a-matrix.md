# 过滤掉矩阵中非空行的 Python 程序

> 原文:[https://www . geeksforgeeks . org/python-过滤掉非空行矩阵的程序/](https://www.geeksforgeeks.org/python-program-that-filters-out-non-empty-rows-of-a-matrix/)

给定矩阵，下面的文章展示了如何过滤矩阵的所有非空行。简单来说，下面提供的代码在移除空行后返回一个矩阵。

> **输入** : test_list = [[4，5，6，7]，[]，[]，[9，8，1]，[]]
> **输出** : [[4，5，6，7]，[9，8，1]]
> **解释**:所有空行被删除。
> **输入** : test_list = [[4，5，6，7]，[]，[9，8，1]，[]]
> **输出** : [[4，5，6，7]，[9，8，1]]
> **解释**:所有空行均被删除。

**方法一:** *使用* [*列表理解*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) *和* [*len()*](https://www.geeksforgeeks.org/python-string-length-len/)

在这种情况下，我们检查每一行的长度，如果它的长度大于 0，那么该行将被添加到结果中。

## 蟒蛇 3

```
# initializing list
test_list = [[4, 5, 6, 7], [], [], [9, 8, 1], []]

# printing original lists
print("The original list is : " + str(test_list))

# checking for row lengths using len()
res = [row for row in test_list if len(row) > 0]

# printing result
print("Filtered Matrix " + str(res))
```

**输出:**

> 原列表为:[[4，5，6，7]，[]，[]，[9，8，1]，[]]
> 
> 过滤矩阵[[4，5，6，7]，[9，8，1]]

**方法二:** *使用* [*滤镜()，*](https://www.geeksforgeeks.org/filter-in-python/)*[*λ*](https://www.geeksforgeeks.org/python-lambda/)*和* [*len()*](https://www.geeksforgeeks.org/python-string-length-len/)*

*在本例中，我们使用 filter()和 lambda 函数过滤 w.r.t 长度的行。len()用于获取长度。*

## *蟒蛇 3*

```
*# initializing list
test_list = [[4, 5, 6, 7], [], [], [9, 8, 1], []]

# printing original lists
print("The original list is : " + str(test_list))

# checking for row lengths using len()
# filtering using filter() + lambda
res = list(filter(lambda row: len(row) > 0, test_list))

# printing result
print("Filtered Matrix " + str(res))*
```

***输出:***

> *原列表为:[[4，5，6，7]，[]，[]，[9，8，1]，[]]*
> 
> *过滤矩阵[[4，5，6，7]，[9，8，1]]*