# Python |在列表中分别合并第一个和最后一个元素

> 原文:[https://www . geesforgeks . org/python-merge-first-and-last-elements-list 中的单独元素/](https://www.geeksforgeeks.org/python-merge-first-and-last-elements-separately-in-a-list/)

给定一个列表列表，其中每个子列表只包含两个元素，编写一个 Python 程序分别合并每个子列表的第一个和最后一个元素，最后输出一个包含两个子列表的列表，一个包含所有第一个元素，另一个包含所有最后一个元素。

**示例:**

```py
Input : [['x', 'y'], ['a', 'b'], ['m', 'n']]
Output : [['x', 'a', 'm'], ['y', 'b', 'n']]

Input : [[1, 2], [3, 4], [5, 6], [7, 8]]
Output : [[1, 3, 5, 7], [2, 4, 6, 8]]

```

**方法#1 :** 列表理解和`zip`

```py
# Python3 program to Merge first and last
# elements separately in a list of lists

def merge(lst):

    return [list(ele) for ele in list(zip(*lst))]

# Driver code
lst = [['x', 'y'], ['a', 'b'], ['m', 'n']]
print(merge(lst))
```

**Output:**

```py
[['x', 'a', 'm'], ['y', 'b', 'n']]

```

**接近#2 :** 使用*怒射*阵

首先将给定列表转换为 *numpy* 数组，然后返回该数组的转置，最后将该数组转换为列表。

```py
# Python3 program to Merge first and last
# elements separately in a list of lists
import numpy as np

def merge(lst):
    arr = np.array(lst)
    return arr.T.tolist()

# Driver code
lst = [['x', 'y'], ['a', 'b'], ['m', 'n']]
print(merge(lst))
```

**Output:**

```py
[['x', 'a', 'm'], ['y', 'b', 'n']]

```