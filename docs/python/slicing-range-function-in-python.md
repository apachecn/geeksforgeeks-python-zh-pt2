# Python 中的切片范围()函数

> 原文:[https://www . geesforgeks . org/slicing-range-function-in-python/](https://www.geeksforgeeks.org/slicing-range-function-in-python/)

**`range()`** 允许用户在给定范围内生成一系列数字。根据用户传递给函数的参数数量，用户可以决定该系列数字的开始和结束位置，以及一个数字和下一个数字之间的差异有多大。

*   **开始:**整数，从该整数开始返回整数序列
*   **停止:**整数，在此之前返回整数序列。
    整数的范围以停止-1 结束。

*   **step:** integer value which determines the increment between each integer in the sequence

    **注意:**更多信息请参考 [Python range()函数](https://www.geeksforgeeks.org/python-range-function/?ref=rp)

    **示例:**

    ```py
    # Python Program to  
    # show range() basics 

    # printing a number 
    for i in range(10): 
        print(i, end =" ") 
    print()
    ```

    **输出:**

    ```py
    0 1 2 3 4 5 6 7 8 9 
    ```

    ## 切片范围函数

    在 Python 中，范围对象不是迭代器，而是可迭代的。因此，对 range()函数进行切片不会返回迭代器，而是返回 iterable。

    **示例:**

    ```py
    # Python program to demonstrate
    # slicing of range function

    a = range(100)

    # Slicing range function
    ans = a[:50]
    print(ans)
    ```

    **输出:**

    ```py
    range(0, 50)
    ```

    现在我们的新系列“ans”的数字从 0 到 50(不包括 50)。所以理解这个的一个概括是

    ```py
    a[start : end : the difference between numbers]
    ```

    所以做类似`ans = a[10:89:3]`的事情会有一个从 10 到 89 的数字范围，它们之间相差 3。

    **示例:**

    ```py
    # Python program to demonstrate
    # slicing of range function

    a = range(100)

    # Slicing range function
    ans = a[10:89:3]
    print(ans)

    ans = a[::5]
    print(ans)
    ```

    **输出:**

    ```py
    range(10, 89, 3)
    range(0, 100, 5)
    ```