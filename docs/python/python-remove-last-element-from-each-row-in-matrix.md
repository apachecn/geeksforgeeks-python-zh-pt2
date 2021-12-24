# Python |移除矩阵中每行的最后一个元素

> 原文:[https://www . geesforgeks . org/python-从矩阵每行中删除最后一个元素/](https://www.geeksforgeeks.org/python-remove-last-element-from-each-row-in-matrix/)

有时，在处理矩阵数据时，我们可以在矩阵每行的后端附加一个杂散元素。这有时是不希望的，希望被移除。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环+ `del` +列表切片**
以上功能的组合可用于执行该任务。在本例中，我们对矩阵中的每一行运行一个循环，并使用`del`移除后面的元素。

```
# Python3 code to demonstrate working of
# Remove last element from each row in Matrix
# Using loop + del + list slicing

# initialize list
test_list = [[1, 3, 4], [2, 4, 6], [3, 8, 1]]

# printing original list 
print("The original list : " + str(test_list))

# Remove last element from each row in Matrix
# Using loop + del + list slicing
for ele in test_list: del ele[-1] 

# printing result
print("Matrix after removal of rear element from rows : " + str(test_list))
```

**Output :**

```
The original list : [[1, 3, 4], [2, 4, 6], [3, 8, 1]]
Matrix after removal of rear element from rows : [[1, 3], [2, 4], [3, 8]]

```