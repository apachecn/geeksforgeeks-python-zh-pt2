# Python–自定义切片列表中的子列表最大值

> 原文:[https://www . geesforgeks . org/python-sublist-最大自定义切片列表/](https://www.geeksforgeeks.org/python-sublist-maximum-in-custom-sliced-list/)

有时候，在处理数据时，我们可能会遇到这样的问题:我们需要提取的不是整个列表的最大值，而是某些自定义分解的子列表的最大值。这种问题很特殊，发生在很多领域。让我们讨论执行这项任务的某些方式。

**方法一:使用`itertools.islice() + max()` +列表理解**
以上方法的组合可以解决这个问题。在这种情况下，islice()用于执行自定义切片，列表理解用于迭代，max()用于计算最大值。

```py
# Python3 code to demonstrate
# Sublist Maximum in custom sliced List
# using itertools.islice() + list comprehension
from itertools import islice

# initializing test list
test_list = [1, 5, 3, 7, 8, 10, 11, 16, 9, 12]

# initializing slice list 
slice_list = [2, 1, 3, 4]

# printing original list 
print("The original list : " + str(test_list))

# printing slice list 
print("The slice list : " + str(slice_list))

# using itertools.islice() + list comprehension
# Sublist Maximum in custom sliced List
temp = iter(test_list)
res = [max(list(islice(temp, part))) for part in slice_list]

# print result
print("The variable sliced list maximum is : " + str(res))
```

**Output :**

```py
The original list : [1, 5, 3, 7, 8, 10, 11, 16, 9, 12]
The slice list : [2, 1, 3, 4]
The variable sliced list maximum is : [5, 3, 10, 16]

```