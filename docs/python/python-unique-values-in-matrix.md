# Python |矩阵中的唯一值

> 原文:[https://www . geesforgeks . org/python-矩阵中的唯一值/](https://www.geeksforgeeks.org/python-unique-values-in-matrix/)

有时我们需要在列表中找到唯一的值，这相对容易，前面已经讨论过了。但是我们也可以得到一个矩阵作为输入，也就是一个列表，本文将讨论在列表中寻找唯一性。让我们看看实现这一点的某些方法。

**方法#1:使用`set()` +列表理解**
set 函数可以将单个列表转换为不重复的元素列表，列表理解用于迭代每个列表。

```
# Python3 code to demonstrate
# checking unique values in matrix
# set() + list comprehension

# initializing matrix 
test_matrix = [[1, 3, 1], [4, 5, 3], [1, 2, 4]]

# printing the original matrix
print ("The original matrix is : " + str(test_matrix))

# using set() + list comprehension
# for checking unique values in matrix
res = list(set(i for j in test_matrix for i in j))

# printing result
print ("Unique values in matrix are : " + str(res))
```

**Output:**

```
The original matrix is : [[1, 3, 1], [4, 5, 3], [1, 2, 4]]
Unique values in matrix are : [1, 2, 3, 4, 5]

```

**方法 2:使用`chain() + set()`**
链函数执行类似于列表理解的任务，但速度更快，因为它使用迭代器进行内部处理，因此速度更快。

```
# Python3 code to demonstrate
# checking unique values in matrix
# chain() + set()
from itertools import chain

# initializing matrix 
test_matrix = [[1, 3, 1], [4, 5, 3], [1, 2, 4]]

# printing the original matrix
print ("The original matrix is : " + str(test_matrix))

# using chain() + set()
# for checking unique values in matrix
res = list(set(chain(*test_matrix)))

# printing result
print ("Unique values in matrix are : " + str(res))
```

**Output:**

```
The original matrix is : [[1, 3, 1], [4, 5, 3], [1, 2, 4]]
Unique values in matrix are : [1, 2, 3, 4, 5]

```