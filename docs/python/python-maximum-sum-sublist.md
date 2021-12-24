# Python |最大和子列表

> 原文:[https://www.geeksforgeeks.org/python-maximum-sum-sublist/](https://www.geeksforgeeks.org/python-maximum-sum-sublist/)

我们可以有一个应用程序来找到最大值的列表并打印出来。这看起来是一项相当简单的任务，也可能很容易编码，但是让人手不足来执行同样的任务总是有帮助的，因为这种问题可能会出现在 web 开发中。

**方法一:使用`reduce()` + lambda**
以上两个功能可以帮助我们完成这个特定的任务。lambda 函数完成逻辑和迭代的任务，`reduce` 函数完成返回所需结果的任务。仅适用于 Python 2。

```
# Python code to demonstrate
# maximum sum sublist 
# using reduce() + lambda

# importing functools for reduce()
import functools

# initializing matrix 
test_matrix = [[1, 3, 1], [4, 5, 3], [1, 2, 4]]

# printing the original matrix
print ("The original matrix is : " + str(test_matrix))

# using reduce() + lambda
# maximum sum sublist 
res = functools.reduce(lambda i, j: i if sum(i) > sum(j) 
      else j, test_matrix)

# printing result
print ("Maximum sum sublist is : " + str(res))
```

**Output:**

```
The original matrix is : [[1, 3, 1], [4, 5, 3], [1, 2, 4]]
Maximum sum sublist is : [4, 5, 3]

```