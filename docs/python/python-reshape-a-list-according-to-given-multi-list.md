# Python |根据给定的多列表重塑列表

> 原文:[https://www . geesforgeks . org/python-重塑列表-根据给定的多列表/](https://www.geeksforgeeks.org/python-reshape-a-list-according-to-given-multi-list/)

给定两个列表，一个是单维列表，一个是多维列表，编写 Python 程序根据多维列表的长度重塑单维列表。

**示例:**

```
Input : list1 = [[1], [2, 3], [4, 5, 6]]
        list2 = ['a', 'b', 'c', 'd', 'e', 'f']
Output : [['a'], ['b', 'c'], ['d', 'e', 'f']]

Input : list1 = [[8, 2, 5], [1], [12, 4, 0, 24]]
        list2 = ['m', 'n', 'o', 'p', 'q', 'r', 's', 't']
Output : [['m', 'n', 'o'], ['p'], ['q', 'r', 's', 't']]

```

**方法#1 :** 使用扩展切片

一个简单而天真的方法是使用 for 循环和 Python 扩展切片将 list2 的每个子列表追加到变量“res”中。

```
# Python3 program to reshape a list 
# according to multidimensional list

def reshape(lst1, lst2):
    last = 0
    res = []
    for ele in list1:
        res.append(list2[last : last + len(ele)])
        last += len(ele)

    return res

# Driver code
list1 = [[1], [2, 3], [4, 5, 6]]
list2 = ['a', 'b', 'c', 'd', 'e', 'f']
print(reshape(list1, list2))
```

**Output:**

```
[['a'], ['b', 'c'], ['d', 'e', 'f']]

```

**方法#2 :** *来自 *itertools* 模块*

另一种方法是使用 *itertools* 模块中的 *islice* 功能。 *islice* 有选择地打印其可滴定容器中提到的数值。因此，我们根据列表 1 生成列表 2 的切片，并将其附加到变量“res”中。

```
# Python3 program to reshape a list 
# according to multidimensional list
from itertools import islice

def yieldSublist(lst1, lst2):
    iter2 = iter(lst2)
    for sublist1 in lst1:
        sublist2 = list(islice(iter2, len(sublist1)))
        yield sublist2

def reshape(lst1, lst2):
    res = list()
    for sub2 in yieldSublist(list1, list2):
        res.append(sub2)

    return res

# Driver code
list1 = [[1], [2, 3], [4, 5, 6]]
list2 = ['a', 'b', 'c', 'd', 'e', 'f']
print(reshape(list1, list2))
```

**Output:**

```
[['a'], ['b', 'c'], ['d', 'e', 'f']]

```

**方法#3 :** Python *迭代器*带列表理解

*iter()* 方法返回列表 2 的迭代器，并将其保存在变量“迭代器”中。现在使用列表理解根据列表 1 重塑列表 2。

```
# Python3 program to reshape a list 
# according to multidimensional list

def reshape(lst1, lst2):
    iterator = iter(lst2)
    return [[next(iterator) for _ in sublist] 
                         for sublist in lst1]

# Driver code
list1 = [[1], [2, 3], [4, 5, 6]]
list2 = ['a', 'b', 'c', 'd', 'e', 'f']
print(reshape(list1, list2))
```

**Output:**

```
[['a'], ['b', 'c'], ['d', 'e', 'f']]

```