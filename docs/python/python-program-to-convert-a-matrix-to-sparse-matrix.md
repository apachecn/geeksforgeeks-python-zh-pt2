# 将矩阵转换为稀疏矩阵的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-to-convert-a-matrix-to-sparse-matrix/](https://www.geeksforgeeks.org/python-program-to-convert-a-matrix-to-sparse-matrix/)

给定一个大部分元素为 0 的矩阵，我们需要在 Python 中将这个矩阵转换成稀疏矩阵。

**示例:**

> **输入:**矩阵:
> 1 0 0 0
> 0 2 0 0
> 0 0 3 0
> 0 0 4
> 5 0 0 0 0
> 
> **输出:**稀疏矩阵:
> 0 0 1
> 1 1 2
> 2 2 3
> 3 3 4
> 4 0 5
> 
> **说明:**
> 这里矩阵用 2D 列表表示，稀疏矩阵用**行列值**表示
> 
> 在稀疏矩阵中，第一行是`0 1 1`表示矩阵在第 0 行和第 1 列的值是 1。

**进场:**

1.  创建一个代表稀疏矩阵列表的空列表。
2.  迭代 2D 矩阵来寻找非零元素。
3.  如果元素非零，则创建一个临时空列表。
4.  将行值、列值和非零元素本身追加到临时列表中。
5.  现在将临时列表追加到稀疏矩阵列表中，以便临时列表充当稀疏矩阵列表的子列表。
6.  从矩阵中获取所有非零元素后，显示稀疏矩阵。

上述方法已用于以下程序中的`convertToSparseMatrix()`功能:

```py
# Python program to convert a
# matrix to sparse matrix

# function display a matrix
def displayMatrix(matrix):

    for row in matrix:
        for element in row:
            print(element, end =" ")
        print()

# function to convert the matrix 
# into a sparse matrix
def convertToSparseMatrix(matrix):

    # creating an empty sparse 
    # matrix list
    sparseMatrix =[]

    # searching values greater 
    # than zero
    for i in range(len(matrix)):
        for j in range(len(matrix[0])):
            if matrix[i][j] != 0 :

                # creating a temporaray
                # sublist
                temp = []

                # appending row value, column 
                # value and element into the 
                # sublist 
                temp.append(i)
                temp.append(j)
                temp.append(matrix[i][j])

                # appending the sublist into
                # the sparse matrix list
                sparseMatrix.append(temp)

    # displaying the sparse matrix
    print("\nSparse Matrix: ") 
    displayMatrix(sparseMatrix)                 

# Driver's code
# initializing a normal matrix
normalMatrix =[[1, 0, 0, 0], 
               [0, 2, 0, 0], 
               [0, 0, 3, 0], 
               [0, 0, 0, 4], 
               [5, 0, 0, 0]] 

# displaying the matrix
displayMatrix(normalMatrix)

# converting the matrix to sparse 
# displayMatrix 
convertToSparseMatrix(normalMatrix)       
```

**输出:**

```py
0 1 0 0 
0 0 2 0 
0 3 0 0 
0 0 5 0 
0 0 0 4 

Sparse Matrix: 
0 0 1 
1 1 2 
2 2 3 
3 3 4 
4 0 5 

```