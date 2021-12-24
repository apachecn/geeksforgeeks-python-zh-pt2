# 用 Python 从用户那里获取矩阵输入

> 原文:[https://www . geesforgeks . org/take-matrix-输入-来自 python 中的用户/](https://www.geeksforgeeks.org/take-matrix-input-from-user-in-python/)

矩阵只不过是数据或数字的矩形排列。换句话说，它是数据或数字的矩形数组。矩阵中的水平条目称为“行”，而垂直条目称为“列”。如果一个矩阵有 r 个行数和 c 个列数，那么矩阵的顺序由 **r x c** 给出。矩阵中的每个条目可以是整数值，也可以是浮点值，甚至可以是复数。

**示例:**

```py
// 3 x 4 matrix
     1 2 3 4
M =  4 5 6 7
     6 7 8 9

// 2 x 3 matrix in Python
A = ( [ 2, 5, 7 ],
      [ 4, 7, 9 ] )

// 3 x 4 matrix in Python where entries are floating numbers
B = ( [ 1.0, 3.5, 5.4, 7.9 ],
      [ 9.0, 2.5, 4.2, 3.6 ],
      [ 1.5, 3.2, 1.6, 6.5 ] )
```

在 Python 中，我们可以用不同的方式获取用户输入矩阵。Python 中用户输入矩阵的一些方法如下所示:

**代码#1:**

```py
# A basic code for matrix input from user

R = int(input("Enter the number of rows:"))
C = int(input("Enter the number of columns:"))

# Initialize matrix
matrix = []
print("Enter the entries rowwise:")

# For user input
for i in range(R):          # A for loop for row entries
    a =[]
    for j in range(C):      # A for loop for column entries
         a.append(int(input()))
    matrix.append(a)

# For printing the matrix
for i in range(R):
    for j in range(C):
        print(matrix[i][j], end = " ")
    print()
```

**输出:**

```py
Enter the number of rows:2
Enter the number of columns:3
Enter the entries rowwise:
1
2
3
4
5
6

1 2 3 
4 5 6 

```

一个内胆:

```py
# one-liner logic to take input for rows and columns
mat = [[int(input()) for x in range (C)] for y in range(R)]
```

**代码#2:** 使用`map()`功能和`Numpy`。

在 Python 中，有一个流行的库叫做***【NumPy】***。这个库是任何科学计算的基础库。它也用于多维数组，因为我们知道矩阵是一个矩形数组，我们将使用这个库为用户输入矩阵。

```py
import numpy as np

R = int(input("Enter the number of rows:"))
C = int(input("Enter the number of columns:"))

print("Enter the entries in a single line (separated by space): ")

# User input of entries in a 
# single line separated by space
entries = list(map(int, input().split()))

# For printing the matrix
matrix = np.array(entries).reshape(R, C)
print(matrix)
```

**输出:**

```py
Enter the number of rows:2
Enter the number of columns:2
Enter the entries in a single line separated by space: 1 2 3 1 
[[1 2]
 [3 1]]
```