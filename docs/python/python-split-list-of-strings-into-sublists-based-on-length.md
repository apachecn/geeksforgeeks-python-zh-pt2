# Python |根据长度将字符串列表拆分为子列表

> 原文:[https://www . geesforgeks . org/python-基于长度将字符串列表拆分为子列表/](https://www.geeksforgeeks.org/python-split-list-of-strings-into-sublists-based-on-length/)

给定一个字符串列表，编写一个 Python 程序，根据字符串长度将列表分成子列表。

**示例:**

```
Input : ['The', 'art', 'of', 'programming']
Output : [['of'], ['The', 'art'], ['programming']]

Input : ['Welcome', 'to', 'geeksforgeeks']
Output : [['to'], ['Welcome'], ['geeksforgeeks']]

```

**方法#1 :** 皮托尼天真

上述方法的一种简单方法是使用字典和 for 循环遍历列表。在每次迭代中，它检查元素长度是否已经在列表中。如果不是，则添加元素长度和元素为`key:value`对，否则，元素只是添加到值子列表中。最后，我们列出字典的所有值并返回它。

```
# Python3 program to Divide list of strings 
# into sublists based on string length

def divideList(lst):
    dct = {}

    for element in lst:
        if len(element) not in dct:
            dct[len(element)] = [element]
        elif len(element) in dct:
            dct[len(element)] += [element]

    res = []
    for key in sorted(dct):
        res.append(dct[key])

    return res

# Driver code
lst = ['The', 'art', 'of', 'programming']
print(divideList(lst))
```

**Output:**

```
[['of'], ['The', 'art'], ['programming']]

```

**从集合模块接近#2 :** `defaultdict()`

该方法使用 *defaultdict* 并将其保存在变量“group_by_len”中。使用 for 循环，我们将字符串的长度保存为键，并将键长度保存为值。最后，我们列出“group_by_len”的所有值并返回它。

```
# Python3 program to Divide list of strings 
# into sublists based on string length
from collections import defaultdict

def divideList(lst):
    group_by_len = defaultdict(list)
    for ele in lst:
        group_by_len[len(ele)].append(ele)

    res = []
    for key in sorted(group_by_len):
        res.append(group_by_len[key])

    return res

# Driver code
lst = ['The', 'art', 'of', 'programming']
print(divideList(lst))
```

**Output:**

```
[['of'], ['The', 'art'], ['programming']]

```

**从 *itertools* 模块接近#3 :** `groupby()`

解决给定问题的最有效和最简单的方法是使用来自 *itertools* 模块的`groupby()`。这是一个单行代码，我们使用两个变量“l”(表示长度)和“g”(字符串组)遍历“lst”，按长度分组，最后返回列表中打包的所有组。

```
# Python3 program to Divide list of strings 
# into sub lists based on string length
from itertools import groupby

def divideList(lst):
    res = dict((l, list(g)) for l, g in groupby(lst, key = len))

    # Sorting dict by key
    res = sorted(res.items(), key = lambda kv:(kv[0], kv[1]))

    # Removing key from list of tuple
    return [el[1:] for el in (tuple(x) for x in res)]

# Driver code
lst = ['The', 'art', 'of', 'programming']
print(divideList(lst))
```

**Output:**

```
[(['of'],), (['The', 'art'],), (['programming'],)]

```