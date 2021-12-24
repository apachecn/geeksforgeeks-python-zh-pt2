# Python |将列表与列表列表中的公共元素合并

> 原文:[https://www . geeksforgeeks . org/python-合并-列表-列表列表中具有公共元素的列表/](https://www.geeksforgeeks.org/python-merge-list-with-common-elements-in-a-list-of-lists/)

给定一个列表，我们必须合并所有具有公共元素的子列表。这类问题在大学考试和解决编码竞赛中非常常见。
下面是实现这一点的一些方法。

```
Input:
[[11, 27, 13], [11, 27, 55], [22, 0, 43], 
 [22, 0, 96], [13, 27, 11], [13, 27, 55], 
 [43, 0, 22], [43, 0, 96], [55, 27, 11]]

Output:
[[0, 43, 96, 22], [27, 11, 13, 55]]

```

**方法# 1:使用递归**是合并所有具有公共元素的子列表的最暴力的方法

```
# Python code to merge all sublist having common elements.

# Using recursion to merge all sublist having common elements.
def merge(Input, _start, _c = [], _seen = [], _used=[]):
    elem = [x for x in Input if any(y in _start for y in x) 
    and x not in _seen and x not in _used]
    if not elem:
        yield set(_c)
        for x in Input:
            if x != _start and x not in _used:
                yield from merge(Input, x, _c=[], _seen=[], 
                           _used=_used+[x, *elem])
    else:
        yield from merge(Input, _start, _c = _c + [x for
                                            y in elem for x in y],
                    _seen=_seen + elem, _used = _used + elem)

#Input list Initialization
Input = [[11, 27, 13], [11, 27, 55], [22, 0, 43],
         [22, 0, 96], [13, 27, 11], [13, 27, 55],
         [43, 0, 22], [43, 0, 96], [55, 27, 11]]

#Calling merge function
Output = list(map(list, {tuple(x) for
                         x in merge(Input, Input[0], _seen=[Input[0]])
                         if x}))

#Printing output
print("Initial list of list is :")
print(Input)
print("List of list after merging is:")
print(Output)
```

```
Output:
Initial list of list is :
[[11, 27, 13], [11, 27, 55], [22, 0, 43], [22, 0, 96],
 [13, 27, 11], [13, 27, 55], [43, 0, 22], [43, 0, 96],
 [55, 27, 11]]
List of list after merging is:
[[0, 43, 96, 22], [27, 11, 13, 55]]

```

**方法 2:使用连通组件**，我们可以将元素建模为，并在连通组件问题中对其进行建模。

```
#Python code to merge all sublist having common elements.

#Importing 
from collections import defaultdict

#merge function to  merge all sublist having common elements.
def merge_common(lists):
    neigh = defaultdict(set)
    visited = set()
    for each in lists:
        for item in each:
            neigh[item].update(each)
    def comp(node, neigh = neigh, visited = visited, vis = visited.add):
        nodes = set([node])
        next_node = nodes.pop
        while nodes:
            node = next_node()
            vis(node)
            nodes |= neigh[node] - visited
            yield node
    for node in neigh:
        if node not in visited:
            yield sorted(comp(node))

#Input list initialization
Input = [['z','x','y'], ['y','g','e'], ['z'],['x','p'],
         ['a','b'], ['y','a'], ['d','g']]

#Calling merge function
Output = list(merge_common(Input))

#Printing function
print("Initial list of list is :")
print(Input)

print("List of list after merging is:")
print(Output)
```

```
Output:
Initial list of list is :
[['z', 'x', 'y'], ['y', 'g', 'e'], ['z'], ['x', 'p'], ['a', 'b'], ['y', 'a'], ['d', 'g']]
List of list after merging is:
[['a', 'b', 'd', 'e', 'g', 'p', 'x', 'y', 'z']]

```