# Python |矩阵中非重复值求和

> 原文:[https://www . geesforgeks . org/python-非重复值-矩阵求和/](https://www.geeksforgeeks.org/python-non-repeating-value-summation-in-matrix/)

有时我们需要在一个列表中找到唯一的值，这相对容易，它的求和和前面已经讨论过了。但是我们也可以得到一个矩阵作为输入，也就是一个列表，本文将讨论在列表中寻找唯一性。让我们看看实现这一点的某些方法。

**方法#1:使用`set() + list comprehension + sum()`**
set 函数可以将单个列表转换为不重复的元素列表，列表理解用于迭代每个列表。使用 sum()执行求和任务。

```
# Python3 code to demonstrate
# Non-Repeating value Summation in Matrix
# set() + list comprehension + sum()

# initializing matrix 
test_matrix = [[1, 3, 1], [4, 5, 3], [1, 2, 4]]

# printing the original matrix
print ("The original matrix is : " + str(test_matrix))

# using set() + list comprehension + sum()
# Non-Repeating value Summation in Matrix
res = sum(list(set(i for j in test_matrix for i in j)))

# printing result
print ("Unique values summation in matrix are : " + str(res))
```

**Output :**

```
The original matrix is : [[1, 3, 1], [4, 5, 3], [1, 2, 4]]
Unique values summation in matrix are : 15

```