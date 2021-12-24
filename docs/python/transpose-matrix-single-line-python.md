# Python 中单行转置矩阵

> 原文:[https://www . geesforgeks . org/转置-矩阵-单行-python/](https://www.geeksforgeeks.org/transpose-matrix-single-line-python/)

[矩阵的转置](https://www.geeksforgeeks.org/inplace-m-x-n-size-matrix-transpose/)是一个我们都可以在 python 中非常容易执行的任务(使用嵌套循环)。但是有一些有趣的方法可以在一行中完成同样的工作。
在 Python 中，我们可以将矩阵实现为嵌套列表(列表中的列表)。每个元素都被视为矩阵的一行。例如，m = [[1，2]，[4，5]，[3，6]]表示 3 行 2 列的矩阵。
列表的第一个元素–**m[0]**和第一行第一列的元素–**m[0][0]**。

1.  **Using Nested List Comprehension:** Nested list comprehension are used to iterate through each element in the matrix.In the given example ,we iterate through each element of matrix (m) in column major manner and assign the result to rez matrix which is the transpose of m.

    ```py
    m = [[1,2],[3,4],[5,6]]
    for row in m :
        print(row)
    rez = [[m[j][i] for j in range(len(m))] for i in range(len(m[0]))]
    print("\n")
    for row in rez:
        print(row)
    ```

    **输出:**

    ```py
    [1, 2]
    [3, 4]
    [5, 6]

    [1, 3, 5]
    [2, 4, 6]

    ```

2.  **Using zip:** Zip returns an iterator of tuples, where the i-th tuple contains the i-th element from each of the argument sequences or iterables. In this example we unzip our array using * and then zip it to get the transpose.

    ```py
    matrix=[(1,2,3),(4,5,6),(7,8,9),(10,11,12)]
    for row in matrix:
        print(row)
    print("\n")
    t_matrix = zip(*matrix)
    for row in t_matrix:
        print(row)
    ```

    **输出:**

    ```py
    (1, 2, 3)
    (4, 5, 6)
    (7, 8, 9)
    (10, 11, 12)

    (1, 4, 7, 10)
    (2, 5, 8, 11)
    (3, 6, 9, 12)

    ```

    注意:-如果您希望结果为[[1，4，7，10][2，5，8，11][3，6，9，12]]形式，可以使用 t_matrix=map(list，zip(*matrix))。

3.  **Using numpy:** NumPy is a general-purpose array-processing package designed to efficiently manipulate large multi-dimensional arrays. The transpose method returns a transposed view of the passed multi-dimensional matrix.

    ```py
    # You need to install numpy in order to import it
    # Numpy transpose returns similar result when 
    # applied on 1D matrix
    import numpy 
    matrix=[[1,2,3],[4,5,6]]
    print(matrix)
    print("\n")
    print(numpy.transpose(matrix))
    ```

    或者，简单地使用”。变量后的“t”

    ```py
    # You need to install numpy in order to import it
    import numpy as np
    matrix = np.array([[1,2,3],[4,5,6]])
    print(matrix)
    print("\n")
    print(matrix.T)
    ```

    **输出:**

    ```py
    [[1 2 3]
     [4 5 6]]

    [[1 4]
     [2 5]
     [3 6]]

    ```

    注:-”。“t”只适用于 numpy 数组

本文由 **Mayank Rawat** &供稿，经**医学博士 Tahmid Hasan** 简单修改。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。