# Python |打印圆形范围内的列表元素

> 原文:[https://www . geesforgeks . org/python-print-list-elements-in-circular-range/](https://www.geeksforgeeks.org/python-print-list-elements-in-circular-range/)

给定一个元素列表，任务是在循环范围内打印一组 *k* 直到 *n 次迭代*的元素。

**示例:**

```py
Input: list = [1, 2, 3, 4, 5, 6, 7], k = 3, n =10
Output: 
[1, 2, 3]
[4, 5, 6]
[7, 1, 2]
[3, 4, 5]
[6, 7, 1]
[2, 3, 4]
[5, 6, 7]
[1, 2, 3]
[4, 5, 6]
[7, 1, 2]

Input: list = [10, 20, 30, 40, 50, 60, 70], k = 4, n = 5
Output: 
[10, 20, 30, 40]
[50, 60, 70, 10]
[20, 30, 40, 50]
[60, 70, 10, 20]
[30, 40, 50, 60]

```

我们可以用`itertools` 配合`zip`来做这个任务。

**示例#1:**

```py
# Python code to print element in group
# of 5 till 9 iteration in circular range.

# Importing
from itertools import cycle

# list initialization
List = [90, 99, 192, 0, 43, 55]

# Defining no of iterations
n = 9

# Defining no of grouping
k = 5

for index, *ans in zip(range(n), *[cycle(List)] * k):
    # printing ans
    print(ans)
```

**Output:**

```py
[90, 99, 192, 0, 43]
[55, 90, 99, 192, 0]
[43, 55, 90, 99, 192]
[0, 43, 55, 90, 99]
[192, 0, 43, 55, 90]
[99, 192, 0, 43, 55]
[90, 99, 192, 0, 43]
[55, 90, 99, 192, 0]
[43, 55, 90, 99, 192]

```

**例 2:**

```py
# Python code to print element in group
# of 6 till 4 iteration in circular range.

# Importing
from itertools import cycle

# list initialization
List = ['Geeks', 'for', 'geeks', 'is', 'portal']

# Defining no of iterations
n = 4

# Defining no of grouping
k = 6

for index, *ans in zip(range(n), *[cycle(List)] * k):
    # printing ans
    print(ans)
```

**Output:**

```py
['Geeks', 'for', 'geeks', 'is', 'portal', 'Geeks']
['for', 'geeks', 'is', 'portal', 'Geeks', 'for']
['geeks', 'is', 'portal', 'Geeks', 'for', 'geeks']
['is', 'portal', 'Geeks', 'for', 'geeks', 'is']

```