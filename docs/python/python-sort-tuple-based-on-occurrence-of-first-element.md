# Python |基于第一个元素的出现对元组进行排序

> 原文:[https://www . geesforgeks . org/python-sort-tuple-基于第一个元素的出现次数/](https://www.geeksforgeeks.org/python-sort-tuple-based-on-occurrence-of-first-element/)

给定一个元组列表，编写一个 Python 程序，根据元组第一个元素的出现对列表进行排序。

**示例:**

```
Input : [(1, 'Jake'), (2, 'Bob'), (1, 'Cara')]
Output : [(1, 'Jake', 'Cara', 2), (2, 'Bob', 1)]

Input : [('b', 'ball'), ('a', 'arm'), ('b', 'b'), ('a', 'ant')]
Output : [('a', 'arm', 'ant', 2), ('b', 'ball', 'b', 2)]

```

**使用`dict.fromkeys`接近#1 :**

`fromkeys()`方法返回一个新的字典，给定的元素序列作为字典的键。现在，一旦我们将新字典存储在' dct '中，我们就可以轻松地迭代' dct '元素并输出所需的元素。

```
# Python3 program to Sort tuple based 
# on occurrence of first element
def sortOnOccurence(lst):
    dct = {}
    for i, j in lst:
        dct.setdefault(i, []).append(j)
    return([(i, *dict.fromkeys(j), len(j))
                 for i, j in dct.items()])

# Driver code
lst = [(1, 'Jake'), (2, 'Bob'), (1, 'Cara')]
print(sortOnOccurence(lst))
```

**Output:**

```
[(1, 'Cara', 'Jake', 2), (2, 'Bob', 1)]

```

**从集合模块中接近#2 :** `OrderedDict`

这种方法是上述方法的替代方法。我们遵循类似的方法，但略有变化，在使用 *OrderedDict* 迭代“dct”时连接元组。

```
# Python3 program to Sort tuple based 
# on occurrence of first element
from collections import OrderedDict

def sortOnOccurence(lst):
    dct = {}
    for i, j in lst:
        dct.setdefault(i, []).append(j)
    return([(k, ) + tuple(OrderedDict.fromkeys(v)) + (len(v), )
    for k, v in dct.items()])

# Driver code
lst = [(1, 'Jake'), (2, 'Bob'), (1, 'Cara')]
print(sortOnOccurence(lst))
```

**Output:**

```
[(1, 'Jake', 'Cara', 2), (2, 'Bob', 1)]

```