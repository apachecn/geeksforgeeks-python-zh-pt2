# Python |用序号

替换列表元素

> 原文:[https://www . geeksforgeeks . org/python-replace-list-elements-with-its-序数/](https://www.geeksforgeeks.org/python-replace-list-elements-with-its-ordinal-number/)

给定一个列表列表，编写一个 Python 程序，用序号值替换内部列表中的值。

**示例:**

```
Input : [[1, 2, 3], [ 4, 5, 6], [ 7, 8, 9, 10]]
Output : [[0, 0, 0], [1, 1, 1], [2, 2, 2, 2]]

Input : [['a'], [ 'd', 'e', 'b', 't'], [ 'x', 'l']]
Output : [[0], [1, 1, 1, 1], [2, 2]]

```

**进场#1 :** 幼稚进场

这个方法是一个单行的朴素方法，其中我们使用两个 for 循环，分别使用 *i* 和 *j* 变量，并遍历每个内部列表，用 *i <sup>th</sup>* 序数替换它。

```
# Python3 program to Replace element
# in a list with its ordinal number 

def replaceOrdinal(lst):
    return [[i for j in range(len(lst[i]))] 
    for i in range(len(lst))]

# Driver Code
lst = [[1, 2, 3], [ 4, 5, 6], [ 7, 8, 9, 10]]
print(replaceOrdinal(lst))
```

**Output:**

```
[[0, 0, 0], [1, 1, 1], [2, 2, 2, 2]]

```

**方法 2 :** 皮托尼天真

这是另一种天真的方法，但更多的是*python*。对于每个内部列表，它返回第 i <sup>个</sup>位置(这是它的序数)，然后将其乘以该特定内部列表的长度，以便返回所需的输出。

```
# Python3 program to Replace element
# in a list with its ordinal number 

def replaceOrdinal(lst):
    return [[i]*len(lst[i]) for i in range(len(lst))]

# Driver Code
lst = [[1, 2, 3], [ 4, 5, 6], [ 7, 8, 9, 10]]
print(replaceOrdinal(lst))
```

**Output:**

```
[[0, 0, 0], [1, 1, 1], [2, 2, 2, 2]]

```

**方法 3 :** 使用 Python `enumerate()`方法
我们可以使用列表理解和 Python `enumerate()`。此方法向 iterable 添加计数器，并以枚举对象的形式返回它。这个计数器索引将被用作序数。因此，我们为内部子列表的每个元素返回各自的计数器索引。

```
# Python3 program to Replace element
# in a list with its ordinal number 

def replaceOrdinal(lst):
    return [[idx for _ in sublist] 
    for idx, sublist in enumerate(lst)]

# Driver Code
lst = [[1, 2, 3], [ 4, 5, 6], [ 7, 8, 9, 10]]
print(replaceOrdinal(lst))
```

**Output:**

```
[[0, 0, 0], [1, 1, 1], [2, 2, 2, 2]]

```

**方法#4 :** 替代使用`enumerate()`
这里，我们以与上述方法类似的方法使用 Python `enumerate()`，但是我们遵循*方法#4* 来生成内部列表，而不是另一个循环。

```
# Python3 program to Replace element
# in a list with its ordinal number 

def replaceOrdinal(lst):
    return [[index] * len(sublist) for index,
    sublist in enumerate(lst)]

# Driver Code
lst = [[1, 2, 3], [ 4, 5, 6], [ 7, 8, 9, 10]]
print(replaceOrdinal(lst))
```

**Output:**

```
[[0, 0, 0], [1, 1, 1], [2, 2, 2, 2]]

```