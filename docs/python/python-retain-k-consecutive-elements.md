# Python |保留 K 个连续元素

> 原文:[https://www . geeksforgeeks . org/python-retain-k-continuous-elements/](https://www.geeksforgeeks.org/python-retain-k-consecutive-elements/)

有时在处理数据时，我们会遇到一个问题，需要选择一些连续出现 K 次的元素。这个问题可能发生在许多领域。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`groupby()` +列表理解**
该任务可以使用上述功能执行。在这种情况下，我们将连续出现的所有数字分组。我们使用列表理解来迭代列表。

```
# Python3 code to demonstrate working of
# Retain K consecutive elements
# using groupby() + list comprehension
from itertools import groupby

# initialize list 
test_list = [1, 1, 4, 5, 5, 6, 7, 7, 8]

# printing original list 
print("The original list : " + str(test_list))

# initialize K 
K = 2

# Retain K consecutive elements
# using groupby() + list comprehension
res = [i for i, j in groupby(test_list) if len(list(j)) == K]

# printing result
print("The K consecutive elements are : " + str(res))
```

**Output :**

```
The original list : [1, 1, 4, 5, 5, 6, 7, 7, 8]
The K consecutive elements are : [1, 5, 7]

```