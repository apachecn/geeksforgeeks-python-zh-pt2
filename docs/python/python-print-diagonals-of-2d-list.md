# Python |打印 2D 列表对角线

> 原文:[https://www . geesforgeks . org/python-print-对角线-of-2d-list/](https://www.geeksforgeeks.org/python-print-diagonals-of-2d-list/)

给定一个 2D 列表(具有相等长度的子列表)，编写一个 Python 程序来打印给定 2D 列表的两条对角线。

**示例:**

```py
Input : [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
Output : Diagonal 1 - [1, 5, 9]
         Diagonal 2 - [3, 5, 7]

Input : [['a', 'b'], ['c', 'd']]
Output : Diagonal 1 - ['a', 'd']
         Diagonal 2 - ['b', 'c']
```

**方法#1 :** 使用 Python xrange()
我们可以使用单行列表理解和 xrange()函数。 *xrange()* 用于在 for 循环中迭代一定次数。因此，我们在循环的每次迭代中在[i][i]位置打印元素。[蟒蛇 2 的作品]

## 计算机编程语言

```py
# Python2 program to print diagonals in 2D list

def printDiagonal(lst):
    # To print Primary Diagonal
    print('Diagonal 1 -'),
    print([lst[i][i] for i in xrange(len(lst))])

    # To print Secondary Diagonal
    print('Diagonal 2 -'),
    print([lst[i][len(lst)-1-i] for i in xrange(len(lst))])

# Driver code
lst = [[1, 2, 3],
       [4, 5, 6],
       [7, 8, 9]]

printDiagonal(lst)
```

**Output**

```py
Diagonal 1 - [1, 5, 9]
Diagonal 2 - [3, 5, 7]
```

**进场#2 :** 使用范围()
此方法与进场#1 类似。range()的优点是它适用于 Python 的两个版本，即 Python2 和 Python3。

## 蟒蛇 3

```py
# Python3 program to print diagonals in 2D list

def printDiagonal(lst):

    # To print Primary Diagonal
    print('Diagonal 1 - ', end ="")
    print([lst[i][i] for i in range(len(lst))])

    # To print Secondary Diagonal
    print('Diagonal 2 - ', end ="")
    print([lst[i][len(lst)-i-1] for i in range(len(lst))])

# Driver code
lst = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
printDiagonal(lst)
```

**Output**

```py
Diagonal 1 - [1, 5, 9]
Diagonal 2 - [3, 5, 7]
```

**方法#3 :** 使用 enumerate()
Python*enumerate()*也是上述方法的替代方法。它使用两个变量“I”和“r”两次遍历枚举(lst)，并简单地返回“r”的第 i <sup>个</sup>元素。

## 蟒蛇 3

```py
# Python3 program to print diagonals in 2D list

def printDiagonal(lst):
    # To print Primary Diagonal
    print('Diagonal 1 - ', end ="")
    print([r[i] for i, r in enumerate(lst)])

    # To print Secondary Diagonal
    print('Diagonal 2 - ', end ="")
    print([r[~i] for i, r in enumerate(lst)])

# Driver code
lst = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
printDiagonal(lst)
```

**Output**

```py
Diagonal 1 - [1, 5, 9]
Diagonal 2 - [3, 5, 7]
```