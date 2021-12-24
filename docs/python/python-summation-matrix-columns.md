# Python–求和矩阵列

> 原文:[https://www . geesforgeks . org/python-summary-matrix-columns/](https://www.geeksforgeeks.org/python-summation-matrix-columns/)

有时，我们会遇到这样的问题，我们需要找到矩阵中每一列的和，即列表中每个索引的和。这种问题在竞争性编程中很常见，也很有用。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`sum() + list comprehension + zip()`**
需要结合以上方法来解决这个特殊问题。sum 函数用于获取所需的 sum 值，zip 函数提供相似索引的组合，然后使用列表理解创建列表。

```py
# Python3 code to demonstrate
# Summation of each column in Matrix
# using sum() + list comprehension + zip()

# initializing list
test_list = [[3, 7, 6], [1, 3, 5], [9, 3, 2]]

# printing original list
print("The original list : " + str(test_list))

# using sum() + list comprehension + zip()
# Summation of each column in Matrix
res = [sum(idx) for idx in zip(*test_list)]

# print result
print("The Summation of each index list is : " + str(res))
```

**Output :**

```py
The original list : [[3, 7, 6], [1, 3, 5], [9, 3, 2]]
The Summation of each index list is : [13, 13, 13]

```