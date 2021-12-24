# Python 中不同排序技术的变化

> 哎哎哎:# t0]https://www . geeksforgeeks . org/sort-sorted-NP-argsort-NP-lexsortb-python/

这些都是行为非常不同的不同类型的排序技术。让我们研究哪种技术有效，如何使用哪种技术。

*让‘a’成为[号](https://www.geeksforgeeks.org/numpy-in-python-set-1-introduction/)阵*

*   **a.sort()**
    (i)就地排序数组&返回 None
    (ii)返回类型为 None
    (iii)占用空间较少。没有创建副本，因为它直接排序原始数组
    (iv)比排序(a)快

```
# Python code to sort an array in-place
# using a.sort
import numpy as np

# Numpy array created
a = np.array([9, 3, 1, 7, 4, 3, 6])

# unsorted array print
print('Original array:\n', a)

# Return type is None
print('Return type:', a.sort())

# Sorted array output
print('Original array sorted->', a)
```

```
OUTPUT: For a.sort()
Original array:
 [9 3 1 7 4 3 6]
Return type: None
Original array sorted-> [1 3 3 4 6 7 9]

```

*   **排序(a)**
    (i)从旧的&创建一个新的列表返回新的列表，排序后的
    (ii)返回类型是一个列表
    (iii)在创建原始数组的副本时占据更多的空间，然后进行排序
    (iv)比 a.sort()

    ```
    # Python code to create a sorted copy using
    # sorted()
    import numpy as np

    # Numpy array created
    a = np.array([9, 3, 1, 7, 4, 3, 6])

    # unsorted array print
    print('Original array:\n', a)
    b = sorted(a)

    # sorted list returned to b, b type is
    # <class 'list'> 
    print('New array sorted->', b)

    # original array no change
    print('Original array->', a)
    ```

    ```
    OUTPUT:a.sorted()
    Original array:
     [9 3 1 7 4 3 6]
    New array sorted-> [1, 3, 3, 4, 6, 7, 9]
    Original array-> [9 3 1 7 4 3 6]

    ```

    慢*   **np.argsort(a)**
    (i)返回将对数组进行排序的索引
    (ii)返回类型为 numpy 数组
    (iii)在返回新的排序索引数组时占用空间

    ```
    # Python code to demonstrate working of np.argsort
    import numpy as np

    # Numpy array created
    a = np.array([9, 3, 1, 7, 4, 3, 6])

    # unsorted array print
    print('Original array:\n', a)

    # Sort array indices
    b = np.argsort(a)
    print('Sorted indices of original array->', b)

    # To get sorted array using sorted indices
    # c is temp array created of same len as of b
    c = np.zeros(len(b), dtype = int)
    for i in range(0, len(b)):
        c[i]= a[b[i]]
    print('Sorted array->', c)
    ```

    ```
    OUTPUT:np.argsort(a)
    Original array:
     [9 3 1 7 4 3 6]
    Sorted indices of original array-> [2 1 5 4 6 3 0]
    Sorted array-> [1 3 3 4 6 7 9]

    ```

    *   **np.lexsort((b, a))**
    (i) Perform an indirect sort using a sequence of keys
    (ii) Sort by a, then by b
    (iii) Return type ndarray of ints Array of indices that sort the keys along the specified axis
    (iv) Occupies space as a new array of sorted indices pair wise is returned.

    ```
    # Python code to demonstrate working of 
    # np.lexsort()
    import numpy as np

    # Numpy array created
    a = np.array([9, 3, 1, 3, 4, 3, 6]) # First column
    b = np.array([4, 6, 9, 2, 1, 8, 7]) # Second column
    print('column a, column b')
    for (i, j) in zip(a, b):
        print(i, ' ', j)

    ind = np.lexsort((b, a)) # Sort by a then by b
    print('Sorted indices->', ind)
    ```

    ```
    OUTPUT:np.lexsort((b, a))
    column a, column b
    9   4
    3   6
    1   9
    3   2
    4   1
    3   8
    6   7
    Sorted indices-> [2 3 1 5 4 6 0]

    ```

    本文由 **SHAURYA UPPAL** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。