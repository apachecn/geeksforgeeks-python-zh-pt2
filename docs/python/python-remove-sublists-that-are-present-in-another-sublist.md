# Python |移除存在于另一个子列表中的子列表

> 原文:[https://www . geesforgeks . org/python-remove-sublist-在另一个子列表中存在/](https://www.geeksforgeeks.org/python-remove-sublists-that-are-present-in-another-sublist/)

给定一个列表列表，编写一个 Python 程序，从另一个子列表中的列表列表列表中删除子列表。

**示例:**

```py
Input : [['a', 'b', 'c'], ['a', 'c'], ['a', 'b', 'c'], ['d']]
Output : [['a', 'b', 'c'], ['d']]

Input : [[1], [1, 2], [1, 2, 3], [0], [0, 1]]
Output : [[1, 2, 3], [0, 1]]

```

**方法#1 :** 使用 *Python 集*(如果列表顺序无关紧要)

这种方法利用 Python *设置*。创建两个空列表“curr_res”来存储当前子列表，创建“result”来存储最终的子列表。将给定列表中的子列表转换为集合，并按长度以相反的顺序对它们进行排序，这样，只有当每个集合不是 *curr_res* 中任何现有集合的子集时，您才能遍历它们并将每个集合添加到 *curr_res* 中。
这种方法的唯一缺点是它可能会以无序的方式产生结果(因为集合是无序的)。

```py
# Python3 program to remove sublists from
# list of lists that are in another sublist

def removeSublist(lst):
    curr_res = []
    result = []
    for ele in sorted(map(set, lst), key = len, reverse = True):
        if not any(ele <= req for req in curr_res):
            curr_res.append(ele)
            result.append(list(ele))

    return result

# Driver code
lst = [['a', 'b', 'c'], ['a', 'b'], ['a', 'b', 'c'], ['d']]
print(removeSublist(lst))
```

**Output:**

```py
[['c', 'b', 'a'], ['d']]

```

**方法 2 :** 使用 *Python 字典*(如果列表顺序重要)

Dict 可能并不总是产生有序输出，因此您可以使用*集合*模块中的*ordereddct*。

```py
# Python3 program to remove sublists from
# list of lists that are in another sublist
from collections import OrderedDict

def removeSublist(lst):
    curr_result = []
    result = []
    for ele in sorted(map(OrderedDict.fromkeys, lst), key = len, reverse = True):
        if not any(ele.keys() <= req.keys() for req in curr_result):
            curr_result.append(ele)
            result.append(list(ele))

    return result

# Driver code
lst = [['a', 'b', 'c'], ['a', 'b'], ['a', 'b', 'c'], ['d']]
print(removeSublist(lst))
```

**Output:**

```py
[['a', 'b', 'c'], ['d']]

```