# Python |反转元组列表中的每个元组

> 原文:[https://www . geeksforgeeks . org/python-在元组列表中反转每个元组/](https://www.geeksforgeeks.org/python-reverse-each-tuple-in-a-list-of-tuples/)

给定一个元组列表，编写一个 Python 程序来反转给定元组列表中的每个元组。

**示例:**

```
Input : [(1, 2), (3, 4, 5), (6, 7, 8, 9)]
Output : [(2, 1), (5, 4, 3), (9, 8, 7, 6)]

Input : [('a', 'b'), ('x', 'y'), ('m', 'n')]
Output : [('b', 'a'), ('y', 'x'), ('n', 'm')]

```

**方法#1 :** 负步切片

我们可以使用标准的负步骤切片`tup[::-1]`来获得元组的反向，并使用列表理解来获得每个元组的反向。

```
# Python3 program to Reverse 
# each tuple in a list of tuples

def reverseTuple(lstOfTuple):

    return [tup[::-1] for tup in lstOfTuple]

# Driver code
lstOfTuple = [(1, 2), (3, 4, 5), (6, 7, 8, 9)]
print(reverseTuple(lstOfTuple))
```

**Output:**

```
[(2, 1), (5, 4, 3), (9, 8, 7, 6)]

```

**方法 2 :** 使用`reversed()`

Python 内置的`reversed()`方法也可以用来反转列表内的每个元组。

```
# Python3 program to Reverse 
# each tuple in a list of tuples

def reverseTuple(lstOfTuple):

    return [tuple(reversed(tup)) for tup in lstOfTuple]

# Driver code
lstOfTuple = [(1, 2), (3, 4, 5), (6, 7, 8, 9)]
print(reverseTuple(lstOfTuple))
```

**Output:**

```
[(2, 1), (5, 4, 3), (9, 8, 7, 6)]

```

**方法#3 :** 使用`map()`功能

Python *map()* 函数也可以通过将负步长切片映射到元组列表来达到这个目的。

```
# Python3 program to Reverse 
# each tuple in a list of tuples

def reverseTuple(lstOfTuple):

    return list(map(lambda tup: tup[::-1], lstOfTuple))

# Driver code
lstOfTuple = [(1, 2), (3, 4, 5), (6, 7, 8, 9)]
print(reverseTuple(lstOfTuple))
```

**Output:**

```
[(2, 1), (5, 4, 3), (9, 8, 7, 6)]

```