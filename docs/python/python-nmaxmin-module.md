# python nmxmin 模块

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-nmxmin 模块/

一个 **nmaxmin** 模块是 Python 的库，它可以帮助你在给定的列表中找到第 n 个最大值和第 n 个最小值。它直接返回给定索引(n)的最大值或最小值。这里给定的列表不能按排序顺序排列，因为它将遍历列表本身。

**注意:**这里的“n”必须介于“1”和列表长度之间，否则会抛出异常。

### 安装库

这个模块没有内置 Python。你需要从外部安装它。要安装此模块，请在终端中键入以下命令。

```py
pip install nmaxmin 
```

### nmaxmin 的功能

*   **nmaxmin.maxn(l, n)**: This function takes two parameters as input (one is a list and the second is index ‘n’).It will return the nth maximum number from the list as output.

    **例:**

    ```py
    # Importing maxn function  
    # From nmaxmin Library  

    from nmaxmin import nmaxmin

    l =[10, 25, 40, 30, 15, 50, 65, 70]

    a = nmaxmin.maxn(l, 3)
    print("The 2nd maximum number in a list l is ", a) 

    a = nmaxmin.maxn(l, 5)
    print("The 5th maximum number in a list l is ", a) 

    a = nmaxmin.maxn(l, 8)
    print("The 8th maximum number in a list l is ", a)
    ```

    **输出** :

    ```py
    The 2nd maximum number in a list l is  50
    The 5th maximum number in a list l is  30
    The 8th maximum number in a list l is  10
    # Importing minn function  

    ```

*   **nmaxmin.minn(l，n)** :该函数以两个参数作为输入(一个是列表，另一个是索引‘n’)。它将从列表中返回第 n 个最小数字作为输出。

    **例:**

    ```py
    # Importing minn function  
    # From nmaxmin Library  

    from nmaxmin import nmaxmin

    l =[10, 25, 40, 30, 15, 50, 65, 70]

    a = nmaxmin.minn(l, 5)
    print("The 5th minimum number in a list l is ", a) 

    a = nmaxmin.minn(l, 2)
    print("The 2nd minimum number in a list l is ", a) 

    a = nmaxmin.minn(l, 1)
    print("The 1st minimum number in a list l is ", a) 
    ```

    **输出** :

    ```py
    The 5th minimum number in a list l is  40
    The 2nd minimum number in a list l is  15
    The 1st minimum number in a list l is  10

    ```