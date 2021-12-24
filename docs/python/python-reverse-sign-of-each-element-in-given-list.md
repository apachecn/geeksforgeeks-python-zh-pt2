# Python |给定列表中每个元素的反符号

> 原文:[https://www . geesforgeks . org/python-给定列表中每个元素的反向符号/](https://www.geeksforgeeks.org/python-reverse-sign-of-each-element-in-given-list/)

给定一个整数列表，编写一个 Python 程序来反转给定列表中每个元素的符号。

**示例:**

```py
Input : [-1, 2, 3, -4, 5, -6, -7]
Output : [1, -2, -3, 4, -5, 6, 7]

Input : [-5, 9, -23, -2, 7]
Output : [5, -9, 23, 2, -7]

```

**方法#1 :** 列表理解

```py
# Python3 program to Convert positive 
# list integers to negative and vice-versa
def Convert(lst):
    return [ -i for i in lst ]

# Driver code
lst = [-1, 2, 3, -4, 5, -6, -7]
print(Convert(lst))
```

**Output:**

```py
[1, -2, -3, 4, -5, 6, 7]

```

**方法#2 :** 使用*numpy*T4【Python 模块，Numpy，也可以使用，这是解决给定问题最 Python 化的方式。首先将列表转换为 numpy 数组，然后返回数组的负数，最后转换为 list。

```py
# Python3 program to Convert positive 
# list integers to negative and vice-versa
import numpy as np

def Convert(lst):
    lst = np.array(lst)
    return list(-lst)

# Driver code
lst = [-1, 2, 3, -4, 5, -6, -7]
print(Convert(lst))
```

**Output:**

```py
[1, -2, -3, 4, -5, 6, 7]

```