# Python–矩阵中最小和的行

> 原文:[https://www . geesforgeks . org/python-带矩阵最小和的行/](https://www.geeksforgeeks.org/python-row-with-minimum-sum-in-matrix/)

我们可以有一个应用程序来查找具有最小值的列表并打印它。这看起来是一项相当简单的任务，也可能很容易编码，但是让人手不足来执行同样的任务总是有帮助的，因为这种问题可能会出现在 web 开发中。

**方法一:使用`reduce()`+λ**
以上两个功能可以帮助我们完成这个特定的任务。lambda 函数执行逻辑和迭代任务，reduce 函数执行返回所需结果的任务。仅适用于 python 2。

```py
# Python code to demonstrate
# Minimum Sum row in Matrix
# using reduce() + lambda

# initializing matrix 
test_matrix = [[1, 3, 1], [4, 5, 3], [1, 2, 4]]

# printing the original matrix
print ("The original matrix is : " + str(test_matrix))

# using reduce() + lambda
# Minimum Sum row in Matrix
res = reduce(lambda i, j: i if sum(i) < sum(j) else j, test_matrix)

# printing result
print ("Minimum sum row is : " + str(res))
```

**Output :**

```py
The original matrix is : [[1, 3, 1], [4, 5, 3], [1, 2, 4]]
Minimum sum row is : [1, 3, 1]

```