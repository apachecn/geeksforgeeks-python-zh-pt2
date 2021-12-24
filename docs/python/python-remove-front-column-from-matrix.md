# Python–从矩阵中移除前列

> 原文:[https://www . geesforgeks . org/python-remove-front-column-from-matrix/](https://www.geeksforgeeks.org/python-remove-front-column-from-matrix/)

有时，在处理矩阵数据时，我们可以在矩阵的每一行的前端附加杂散元素。这有时是不希望的，希望被移除。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环+ del +列表切片**
上述功能的组合可用于执行该任务。在本文中，我们对矩阵中的每一行运行一个循环，并使用 del 移除前面的元素。

```
# Python3 code to demonstrate working of
# Remove front column from Matrix
# Using loop + del + list slicing

# initialize list
test_list = [[1, 3, 4], [2, 4, 6], [3, 8, 1]]

# printing original list 
print("The original list : " + str(test_list))

# Remove front column from Matrix
# Using loop + del + list slicing
for ele in test_list: del ele[0] 

# printing result
print("Matrix after removal of front column : " + str(test_list))
```

**Output :**

```
The original list : [[1, 3, 4], [2, 4, 6], [3, 8, 1]]
Matrix after removal of front column : [[3, 4], [4, 6], [8, 1]]

```