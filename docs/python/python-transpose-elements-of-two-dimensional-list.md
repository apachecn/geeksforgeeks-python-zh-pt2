# Python |转置二维列表元素

> 原文:[https://www . geesforgeks . org/python-转置-二维元素列表/](https://www.geeksforgeeks.org/python-transpose-elements-of-two-dimensional-list/)

给定一个二维整数列表，编写一个 Python 程序来获得给定列表的转置。
在 Python 中，矩阵可以解释为列表的列表。每个元素都被视为矩阵的一行。例如，m = [[10，20]，[40，50]，[30，60]]表示 3 行 2 列的矩阵。列表的第一个元素–m[0]和第一行第一列中的元素–m[0][0]。

**示例:**

```py
Input :  l1 = [[4, 5, 3, 9],
               [7, 1, 8, 2],
               [5, 6, 4, 7]]

Output : lt = [[4, 7, 5],
               [5, 1, 6],
               [3, 8, 4],
               [9, 2, 7]]
```

**方法#1:** 使用循环

## 计算机编程语言

```py
# Python program to get transpose
# elements of two dimension list
def transpose(l1, l2):

    # iterate over list l1 to the length of an item
    for i in range(len(l1[0])):
        # print(i)
        row =[]
        for item in l1:
            # appending to new list with values and index positions
            # i contains index position and item contains values
            row.append(item[i])
        l2.append(row)
    return l2

# Driver code
l1 = [[4, 5, 3, 9], [7, 1, 8, 2], [5, 6, 4, 7]]
l2 = []
print(transpose(l1, l2))
```

**Output**

```py
[[4, 7, 5], [5, 1, 6], [3, 8, 4], [9, 2, 7]]

```

**方法 2:** 使用列表理解

## 计算机编程语言

```py
# Python program to get transpose
# elements of two dimension list
def transpose(l1, l2):

    # we have nested loops in comprehensions
    # value of i is assigned using inner loop
    # then value of item is directed by row[i]
    # and appended to l2
    l2 =[[row[i] for row in l1] for i in range(len(l1[0]))]
    return l2

# Driver code
l1 = [[4, 5, 3, 9], [7, 1, 8, 2], [5, 6, 4, 7]]
l2 = []
print(transpose(l1, l2))
```

**Output**

```py
[[4, 7, 5], [5, 1, 6], [3, 8, 4], [9, 2, 7]]

```

**方法#3:** 使用 numpy

## 蟒蛇 3

```py
# Python program to get transpose
# elements of two dimension list
import numpy

l1= [[4, 5, 3, 9], [7, 1, 8, 2], [5, 6, 4, 7]]
print(numpy.transpose(l1))
```

**输出:**

```py
[[4 7 5]
 [5 1 6]
 [3 8 4]
 [9 2 7]]
```

**方法#4:** 使用 zip 功能

## 计算机编程语言

```py
# Python program to get transpose
# elements of two dimension list
def transpose(l1, l2):

    # star operator will first
    # unpack the values of 2D list
    # and then zip function will
    # pack them again in opposite manner
    l2 = list(map(list, zip(*l1)))
    return l2

# Driver code
l1 = [[4, 5, 3, 9], [7, 1, 8, 2], [5, 6, 4, 7]]
l2 = []
print(transpose(l1, l2))

# code contributed by
# chaudhary_19
# Mayank Chaudhary
# modified by Chirag Shilwant
```

**Output**

```py
[[4, 7, 5], [5, 1, 6], [3, 8, 4], [9, 2, 7]]

```