# Python |合并嵌套列表

> 原文:[https://www.geeksforgeeks.org/python-merging-nested-lists/](https://www.geeksforgeeks.org/python-merging-nested-lists/)

给定两个嵌套列表“lst1”和“lst2”，编写一个 Python 程序，从两个给定的嵌套列表中创建一个新的嵌套列表“lst3”，这样新的嵌套列表由两个列表的公共交集以及不相交的元素组成。

**示例:**

```
Input : lst1 = [[5, 9], [8, 2, 6], [3, 4]]
        lst2 = [[9, 5, 8], [2, 6], [3, 4, 1]]
Output : [[9, 5], [8], [2, 6], [3, 4], [1]]

Input : lst1 = [['a', 'b', 'c'], ['x']]
        lst2 = [['b', 'c', 'y'], ['x', 'y']]
Output : [['b', 'c'], ['x'], ['y'], ['a']]
```

**方法#1 :** 通过使用 *functools.reduce()*
设置交集该方法使用集合交集来计算每个交集，然后添加任何剩余的项目(即，仅出现在两个列表之一上的项目)。我们将首先使用 functools.reduce()生成“lst1”和“lst2”的唯一元素，并将它们分别保存到“temp1”和“temp2”中。之后，在“lst3”中找到两个列表的集合交集。最后，找出“lst1”和“lst2”的对称差，得到只出现在 2 个集合中的一个集合中的项目，并将其附加到“lst3”中。

## 蟒蛇 3

```
# Python3 program to find Greatest common
# intersection of two nested lists
import itertools
import functools

def GCI(lst1, lst2):

    temp1 = functools.reduce(lambda a, b: set(a).union(set(b)), lst1)
    temp2 = functools.reduce(lambda a, b: set(a).union(set(b)), lst2)

    lst3 = [list(set(a).intersection(set(b)))
           for a, b in itertools.product(lst1, lst2)
           if len(set(a).intersection(set(b))) != 0]

    lst3.extend([x] for x in temp1.symmetric_difference(temp2))

    return lst3

# Driver code
lst1 = [[5, 9], [8, 2, 6], [3, 4]]
lst2 = [[9, 5, 8], [2, 6], [3, 4, 1]]
print(GCI(lst1, lst2))
```

**Output:** 

```
[[9, 5], [8], [2, 6], [3, 4], [1]]
```

**方法#2 :** 通过使用*过滤器*
设置交叉点这是一种比方法#1 更有效的方法，因为它简化了交叉点。首先，展平嵌套列表。使用过滤器()获取交集，并将其保存到“lst3”。现在找到不在 lst1 或 lst2 中的元素，并将它们保存到“temp”中。最后，将“temp”追加到“lst3”中。

## 蟒蛇 3

```
# Python3 program to find Greatest common
# intersection of two nested lists
import itertools
from functools import reduce

def GCI(lst1, lst2):

    temp1 = reduce(list.__add__, lst1)
    temp2 = reduce(list.__add__, lst2)
    lst3 = list(filter(None, [list(set(o1) & set(o2))
                     for o1 in lst1 for o2 in lst2])) 

    temp = filter(lambda x : x not in temp1 or x not in temp2,
                                      set(temp1) | set(temp2))
    lst3.append(list(temp))

    return lst3

# Driver code
lst1 = [[5, 9], [8, 2, 6], [3, 4]]
lst2 = [[9, 5, 8], [2, 6], [3, 4, 1]]
print(GCI(lst1, lst2))
```

**Output:** 

```
[[9, 5], [8], [2, 6], [3, 4], [1]]
```