# Python 中使用字典的稀疏矩阵

> 原文:[https://www . geesforgeks . org/sparse-matrix-in-python-using-dictionary/](https://www.geeksforgeeks.org/sparse-matrix-in-python-using-dictionary/)

[稀疏矩阵](https://www.geeksforgeeks.org/how-to-create-a-sparse-matrix-in-python/)是一个矩阵，其中大部分元素的值为零，因此需要存储这种矩阵的有效方法。稀疏矩阵通常用于应用机器学习，例如包含将类别映射到计数的数据编码的数据，以及机器学习的整个子领域，例如自然语言处理。

**例:**

```py
0 0 0 1 0            
2 0 0 0 3
0 0 0 4 0

Above is sparse matrix with only 4 non-zero elements.
```

用 2D 阵列表示稀疏矩阵会导致大量内存的浪费，因为矩阵中的零在大多数情况下是没有用的。所以，我们不是用非零元素存储零，而是只存储非零元素。这些有效的方法只需要将非零值与其索引一起存储，以便在需要时可以检索原始矩阵。Python 中一种有效的方法是使用[字典](https://www.geeksforgeeks.org/python-dictionary/)。Python 中的字典像 Java 中的映射一样以键值对存储数据。字典以无序的方式存储数据。

### 方法:

*   首先，我们取一个稀疏矩阵，创建一个空字典。
*   然后我们遍历矩阵的所有元素，检查它们是零元素还是非零元素。
*   非零元素被添加到字典中，它们的索引作为键，它们的数据作为字典的键值对中的值。
*   最后，我们可以打印字典，给出每个元素及其索引。

下面是实现。

T2T4

```py
# creating sparse matrix
arr = [[0, 0, 0, 1, 0],
       [2, 0, 0, 0, 3],
       [0, 0, 0, 4, 0]]

# creating empty dictionary
dic = {}

# iterating through the matrix
for i in range(len(arr)):
    for j in range(len(arr[i])):
        if arr[i][j] != 0:

            # adding non zero elements to
            # the dictionary
            dic[i, j] = arr[i][j]

print("Position of non-zero elements in the matrix:")
print(dic)
```

T5

**输出:**

> 以下字典显示了非零元素在稀疏矩阵
> 
> {(0，3): 1，(1，0): 2，(1，4): 3，(2，3): 4}