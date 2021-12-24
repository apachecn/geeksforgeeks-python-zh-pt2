# Python–字符串矩阵连接

> 原文:[https://www . geesforgeks . org/python-string-matrix-concation/](https://www.geeksforgeeks.org/python-string-matrix-concatenation/)

有时，在使用 Matrix 时，我们可能会遇到一个问题，即我们有字符串，并且我们需要对其中存在的所有字符串进行通用连接。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `join()`**
我们可以使用列表理解来解决这个问题，作为我们可能用来执行这个特定任务的常规循环的潜在速记。我们只需将提取的元素连接起来，并将其作为单个字符串放入。

```py
# Python3 code to demonstrate
# String Matrix Concatenation
# Using list comprehension

# initializing list
test_list = [["geeksforgeeks", " is", " best"], [" I", " Love"], [" Gfg"]]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension
# count of all the elements in list
res = "".join([ele for sub in test_list for ele in sub])

# print result
print("The Matrix Concatenation is : " + str(res))
```

**Output :**

```py
The original list : [['geeksforgeeks', ' is', ' best'], [' I', ' Love'], [' Gfg']]
The Matrix Concatenation is : geeksforgeeks is best I Love Gfg

```