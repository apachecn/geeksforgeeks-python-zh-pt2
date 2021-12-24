# Python |交替合并两个列表

> 原文:[https://www . geesforgeks . org/python-merge-two-list-alternative/](https://www.geeksforgeeks.org/python-merge-two-lists-alternatively/)

给定两个列表，编写一个 Python 程序以另一种方式合并给定的列表，前提是这两个列表的长度相等。

**示例:**

```
Input : lst1 = [1, 2, 3]
        lst2 = ['a', 'b', 'c']
Output : [1, 'a', 2, 'b', 3, 'c']

Input : lst1 = ['name', 'alice', 'bob']
        lst2 = ['marks', 87, 56]
Output : ['name', 'marks', 'alice', 87, 'bob', 56]

```

**方法一:**列表理解

```
# Python3 program to merge two lists 
# alternatively

def countList(lst1, lst2):
    return [sub[item] for item in range(len(lst2))
                      for sub in [lst1, lst2]]

# Driver code
lst1 = [1, 2, 3]
lst2 = ['a', 'b', 'c']
print(countList(lst1, lst2))
```

**Output:**

```
[1, 'a', 2, 'b', 3, 'c']

```

还有一种使用列表理解的替代方法，如下所示

```
def countList(lst1, lst2):
    return [item for pair in zip(lst1, lst2 + [0])
                                 for item in pair]
```

**方法 2 :** 使用`itertools.cycle()`

```
# Python3 program to merge two lists 
# alternatively
from itertools import cycle

def countList(lst1, lst2):
    iters = [iter(lst1), iter(lst2)]
    return list(iter.__next__() for iter in cycle(iters))

# Driver code
lst1 = [1, 2, 3]
lst2 = ['a', 'b', 'c']
print(countList(lst1, lst2))
```

**Output:**

```
[1, 'a', 2, 'b', 3, 'c']

```

**方法 3 :** 使用`reduce()`

```
# Python3 program to merge two lists 
# alternatively
import operator
from functools import reduce

def countList(lst1, lst2):
    return reduce(operator.add, zip(lst1, lst2))

# Driver code
lst1 = [1, 2, 3]
lst2 = ['a', 'b', 'c']
print(countList(lst1, lst2))
```

**Output:**

```
(1, 'a', 2, 'b', 3, 'c')

```

**方法#4 :** 使用`numpy`模块

```
# Python3 program to merge two lists 
# alternatively
import numpy as np

def countList(lst1, lst2):
    return np.array([[i, j] for i, j in zip(lst1, lst2)]).ravel()

# Driver code
lst1 = [1, 2, 3]
lst2 = ['a', 'b', 'c']
print(countList(lst1, lst2))
```

**Output:**

```
['1' 'a' '2' 'b' '3' 'c']

```