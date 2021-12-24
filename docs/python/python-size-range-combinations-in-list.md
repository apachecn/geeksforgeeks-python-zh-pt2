# Python |列表中的尺寸范围组合

> 原文:[https://www . geesforgeks . org/python-size-range-in-list 组合/](https://www.geeksforgeeks.org/python-size-range-combinations-in-list/)

已经讨论了寻找特定大小的列表元素的组合的问题。但是有时，我们需要更多，我们希望拥有 I 和 j 之间范围内的所有大小的元素的所有组合，让我们讨论执行该功能的某些方法。

**方法#1:使用列表理解+ `combinations()`**
这个任务可以使用列表理解来执行，列表理解可以执行改变组合长度的任务，组合()可以执行寻找组合的实际任务。

```
# Python3 code to demonstrate working of
# Size Range Combinations in list
# Using list comprehension + combinations()
from itertools import combinations

# initializing list
test_list = [4, 5, 6, 7, 3, 8]

# printing original list
print("The original list is : " + str(test_list))

# initializing i, j 
i, j = 2, 4

# Size Range Combinations in list
# Using list comprehension + combinations()
res1 = [com for sub in range(j) for com in combinations(test_list, sub + 1)]
res2 = [com for sub in range(i - 1) for com in combinations(test_list, sub + 1)]
res = list(set(res1) - set(res2))

# Printing result
print("The combinations of elements in range of i and j : " + str(res))
```

**Output :**

> 原列表为:【4、5、6、7、3、8】
> I、j 范围内的元素组合:[(7、3)、(4、7)、(4、5、6、3)、(4、8)、(5、6)、(5、6、3)、(4、6、8)、(5、7、8)、(5、6、7、8)、(6、7、8)、(6、7、3)、(6、7、3、8)、(5、8)、(5、3、8)、(5、6、7)、(6、7)、(4、7、3、8)、(5) 3), (6, 3, 8), (5, 7, 3, 8), (7, 3, 8), (5, 7, 3), (4, 5, 7, 3), (4, 7, 8), (4, 6, 7), (4, 5, 3), (4, 5), (4, 6, 7, 3), (6, 7, 8), (4, 6, 3, 8), (4, 5, 6, 8), (4, 3, 8), (4, 5, 7, 8), (4, 5, 6), (5, 3), (4, 6, 3), (4, 5, 6, 7), (4, 5, 7), (4, 6), (6, 8), (4, 5, 3, 8), (4, 5, 8), (5, 7), (3, 8), (4, 3), (5, 6, 7, 3), (4, 7, 3), (7, 8)]