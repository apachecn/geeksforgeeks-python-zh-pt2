# Python–矩阵数据类型校正

> 原文:[https://www . geesforgeks . org/python-matrix-data-type-correction/](https://www.geeksforgeeks.org/python-matrix-data-type-rectification/)

有时，在处理数据时，我们可能会遇到需要对列表数据类型进行校正的问题，即在必要时将数字字符串转换为数字。这也可以以矩阵形式出现。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `isdigit()`**
这是这个任务可以执行的方式之一。在这种情况下，我们迭代矩阵的每个元素，并使用类型转换检查数字字符串，然后执行转换。

```py
# Python3 code to demonstrate 
# Matrix Data Type Rectification
# using isdigit() + list comprehension

# Initializing list
test_list = [['5', 'GFG'], ['1', '3'], ['is', '11'], ['1', 'best']]

# printing original list
print("The original list is : " + str(test_list))

# Matrix Data Type Rectification
# using isdigit() + list comprehension
res = [[int(ele) if ele.isdigit() else ele for ele in sub] for sub in test_list]

# printing result 
print ("The rectified Matrix is : " + str(res))
```

**Output :**

```py
The original list is : [['5', 'GFG'], ['1', '3'], ['is', '11'], ['1', 'best']]
The rectified Matrix is : [[5, 'GFG'], [1, 3], ['is', 11], [1, 'best']]

```