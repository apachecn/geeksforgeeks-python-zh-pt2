# Python |解包元组列表

> 原文:[https://www . geesforgeks . org/python-解包-列表元组/](https://www.geeksforgeeks.org/python-unpacking-tuple-of-lists/)

给定一个列表元组，编写一个 Python 程序来解包打包在给定元组中的列表元素。

**示例:**

```
Input : (['a', 'apple'], ['b', 'ball'])
Output : ['a', 'apple', 'b', 'ball']

Input : ([1, 'sam', 75], [2, 'bob', 39], [3, 'Kate', 87])
Output : [1, 'sam', 75, 2, 'bob', 39, 3, 'Kate', 87]

```

**使用`reduce()`接近#1 :**

`reduce()`是一个经典的列表操作，用于将参数中传递的特定函数应用于所有列表元素。在这种情况下，我们使用了*运算符*模块的`add`函数，它只是将给定的列表参数添加到一个空列表中。

```
# Python3 program to unpack 
# tuple of lists
from functools import reduce
import operator

def unpackTuple(tup):

    return (reduce(operator.add, tup))

# Driver code
tup = (['a', 'apple'], ['b', 'ball'])
print(unpackTuple(tup))
```

**Output:**

```
['a', 'apple', 'b', 'ball']

```

**方法#2 :** 使用 Numpy[方法#1 的替代方法]

```
# Python3 program to unpack 
# tuple of lists
from functools import reduce
import numpy

def unpackTuple(tup):

    print (reduce(numpy.append, tup))

# Driver code
tup = (['a', 'apple'], ['b', 'ball'])
unpackTuple(tup)
```

**Output:**

```
['a' 'apple' 'b' 'ball']

```

**使用`itertools.chain(*iterables)`接近#3 :**

`itertools.chain(*iterables)`创建一个迭代器，从第一个可迭代表返回元素，直到它用完，然后继续到下一个可迭代表，直到所有的可迭代表都用完。这使我们的工作变得容易得多，因为我们可以简单地将每个 iterable 添加到空列表中并返回它。

```
# Python3 program to unpack 
# tuple of lists
from itertools import chain

def unpackTuple(tup):
    res = []
    for i in chain(*tup):
        res.append(i)

    print(res)

# Driver code
tup = (['a', 'apple'], ['b', 'ball'])
unpackTuple(tup)
```

**Output:**

```
['a', 'apple', 'b', 'ball']

```