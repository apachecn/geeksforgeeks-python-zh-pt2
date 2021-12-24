# Python–删除长度为 K 的元组

> 原文:[https://www . geesforgeks . org/python-remove-长度元组-k/](https://www.geeksforgeeks.org/python-remove-tuples-of-length-k/)

给定元组列表，移除所有长度为 k 的元组。

> **输入** : test_list = [(4，5)，(4)，(8，6，7)，(1)，(3，4，6，7)]，K = 2
> **输出** : [(4，，(8，6，7)，(1)，(3，4，6，7)]
> **解释** : (4，len = 2 的删除。
> 
> **输入** : test_list = [(4，5)、(4)、(5)、(8，6，7)、(1)、(3，4，6，7)]，K = 3
> **输出** : [(4，5)、(4)、(1)、(3，4，6，7)]
> **解释** : 3 长度元组被移除。

**方法一:使用列表理解**

这是执行这项任务的方法之一。在这种情况下，我们对循环中的所有元素进行迭代，并使用条件执行移除 K 个长度元素的所需任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Remove Tuples of Length K
# Using list comprehension

# initializing list
test_list = [(4, 5), (4, ), (8, 6, 7), (1, ), (3, 4, 6, 7)]

# printing original list
print("The original list : " + str(test_list))

# initializing K 
K = 1

# 1 liner to perform task
# filter just lengths other than K 
# len() used to compute length
res = [ele for ele in test_list if len(ele) != K]

# printing result 
print("Filtered list : " + str(res))
```

**Output**

```py
The original list : [(4, 5), (4, ), (8, 6, 7), (1, ), (3, 4, 6, 7)]
Filtered list : [(4, 5), (8, 6, 7), (3, 4, 6, 7)]

```

**方法 2:使用滤镜()+λ+len()**

解决这个问题的另一种方法。在本文中，我们使用 filter()和 lambda 函数执行过滤，以使用 len()仅提取非 K 长度元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Remove Tuples of Length K
# Using filter() + lambda + len() 

# initializing list
test_list = [(4, 5), (4, ), (8, 6, 7), (1, ), (3, 4, 6, 7)]

# printing original list
print("The original list : " + str(test_list))

# initializing K 
K = 1

# filter() filters non K length values and returns result
res = list(filter(lambda x : len(x) != K, test_list))

# printing result 
print("Filtered list : " + str(res))
```

**Output**

```py
The original list : [(4, 5), (4, ), (8, 6, 7), (1, ), (3, 4, 6, 7)]
Filtered list : [(4, 5), (8, 6, 7), (3, 4, 6, 7)]

```