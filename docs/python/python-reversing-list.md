# 在 Python 中反转列表

> 原文:[https://www.geeksforgeeks.org/python-reversing-list/](https://www.geeksforgeeks.org/python-reversing-list/)

Python 为我们提供了各种反转列表的方法。关于 python 中的列表如何反转，我们将介绍许多技术中的一些。
示例:

```py
Input : list = [10, 11, 12, 13, 14, 15]
Output : [15, 14, 13, 12, 11, 10]

Input : list = [4, 5, 6, 7, 8, 9]
Output : [9, 8, 7, 6, 5, 4]

```

**方法 1:使用反向()内置函数。**
在这个方法中，我们既没有就地反转列表(修改原始列表)，也没有创建列表的任何副本。相反，我们得到一个反向迭代器，用来循环遍历列表。

```py
# Reversing a list using reversed()
def Reverse(lst):
    return [ele for ele in reversed(lst)]

# Driver Code
lst = [10, 11, 12, 13, 14, 15]
print(Reverse(lst))
```

输出:

```py
[15, 14, 13, 12, 11, 10]

```

**方法二:使用反向()内置功能。**
使用 reverse()方法，我们可以将列表对象**中的内容进行就地反转**，也就是说，我们不需要创建新的列表，而是按照相反的顺序将现有元素复制到原始列表中。此方法直接修改原始列表。

```py
# Reversing a list using reverse()
def Reverse(lst):
    lst.reverse()
    return lst

lst = [10, 11, 12, 13, 14, 15]
print(Reverse(lst))
```

输出:

```py
[15, 14, 13, 12, 11, 10]

```

**方法 3:采用切片技术。**
在这种技术中，会制作一份列表的副本，并且列表不会就地排序。创建副本需要更多空间来容纳所有现有元素。这会耗尽更多的内存。

```py
# Reversing a list using slicing technique
def Reverse(lst):
    new_lst = lst[::-1]
    return new_lst

lst = [10, 11, 12, 13, 14, 15]
print(Reverse(lst))
```

输出:

```py
[15, 14, 13, 12, 11, 10]

```

要更好地理解切片技术，请参考 Python 中的[切片技术](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)。