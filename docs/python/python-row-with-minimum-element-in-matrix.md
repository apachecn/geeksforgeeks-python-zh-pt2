# Python |矩阵中元素最少的行

> 原文:[https://www . geesforgeks . org/python-矩阵中元素最少的行/](https://www.geeksforgeeks.org/python-row-with-minimum-element-in-matrix/)

我们可以有一个应用程序来查找具有最小值的列表并打印它。这似乎是一项相当简单的任务，也可能很容易编码，但有时我们需要打印包含它的整行，让人手不足来执行同样的操作总是有帮助的，因为这种问题可能会出现在 web 开发中。让我们讨论执行这项任务的某些方法。

**方法一:使用`reduce()`+λ**
以上两个功能可以帮助我们完成这个特定的任务。lambda 函数执行逻辑和迭代任务，reduce 函数执行返回所需结果的任务。仅适用于 python 2。

```py
# Python code to demonstrate
# Row with Minimum element in Matrix
# using reduce() + lambda

# initializing matrix 
test_matrix = [[1, 3, 1], [4, 5, 3], [7, 2, 4]]

# printing the original matrix
print ("The original matrix is : " + str(test_matrix))

# using reduce() + lambda
# Row with Minimum element in Matrix
res = reduce(lambda i, j: i if min(i) < min(j) else j, test_matrix)

# printing result
print ("Minimum element sublist is : " + str(res))
```

**Output :**

```py
The original matrix is : [[1, 3, 1], [4, 5, 3], [7, 2, 4]]
Minimum element sublist is : [1, 3, 1]

```