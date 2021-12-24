# Python–K 索引处有值的记录

> 原文:[https://www . geeksforgeeks . org/python-带值记录 at-k-index/](https://www.geeksforgeeks.org/python-records-with-value-at-k-index/)

有时，在处理记录时，我们可能会遇到一个问题，即我们需要在元组的特定 Kth 位置找到特定值的元素的所有元组。这似乎是一个特殊的问题，但是在处理记录中的许多键时，我们会遇到这个问题。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用循环**
这是解决这个问题的蛮力方法。在这种情况下，如果我们在元组中的第 Kt 个位置找到特定记录，我们将进行检查并追加到列表中。

```
# Python3 code to demonstrate working of
# Records with Value at K index
# Using loop

# initialize list 
test_list = [(3, 1, 5), (1, 3, 6), (2, 5, 7), (5, 2, 8), (6, 3, 0)]

# printing original list
print("The original list is : " + str(test_list))

# initialize ele 
ele = 3

# initialize K 
K = 1

# Records with Value at K index
# Using loop
# using y for K = 1 
res = []
for x, y, z in test_list:
    if y == ele:
        res.append((x, y, z))

# printing result
print("The tuples of element at Kth position : " + str(res))
```

**Output :**

```
The original list is : [(3, 1, 5), (1, 3, 6), (2, 5, 7), (5, 2, 8), (6, 3, 0)]
The tuples of element at Kth position : [(1, 3, 6), (6, 3, 0)]

```