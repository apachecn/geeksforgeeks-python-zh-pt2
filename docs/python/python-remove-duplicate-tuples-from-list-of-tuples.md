# Python |从元组列表中删除重复元组

> 原文:[https://www . geesforgeks . org/python-从元组列表中删除重复元组/](https://www.geeksforgeeks.org/python-remove-duplicate-tuples-from-list-of-tuples/)

给定一个元组列表，编写一个 Python 程序从给定列表中移除所有重复的元组。

**示例:**

```
Input : [(1, 2), (5, 7), (3, 6), (1, 2)]
Output : [(1, 2), (5, 7), (3, 6)]

Input : [('a', 'z'), ('a', 'x'), ('z', 'x'), ('a', 'x'), ('z', 'x')]
Output : [('a', 'z'), ('a', 'x'), ('z', 'x')]

```

**方法#1 :** 列表理解

这是一种使用列表理解的幼稚方法。这里，我们使用两个*用于*循环，*设置*数据结构来消除所有重复。

```
# Python3 program to remove duplicate 
# tuples from list of tuples

def removeDuplicates(lst):

    return [t for t in (set(tuple(i) for i in lst))]

# Driver code
lst = [(1, 2), (5, 7), (3, 6), (1, 2)]
print(removeDuplicates(lst))
```

**Output:**

```
[(1, 2), (5, 7), (3, 6)]

```

**方法 2 :** 列表理解(有效方法)

与上面的方法相比，这种方法是有效的，这里我们在列表理解中使用单个 for 循环，然后将其转换为 set 以移除重复项，然后再次将其转换为 list。

```
# Python3 program to remove duplicate 
# tuples from list of tuples

def removeDuplicates(lst):

    return list(set([i for i in lst]))

# Driver code
lst = [(1, 2), (5, 7), (3, 6), (1, 2)]
print(removeDuplicates(lst))
```

**Output:**

```
[(1, 2), (5, 7), (3, 6)]

```

**法#3 :** 蟒*枚举()*法

```
# Python3 program to remove duplicate 
# tuples from list of tuples

def removeDuplicates(lst):

    return [[a, b] for i, [a, b] in enumerate(lst) 
    if not any(c == b for _, c in lst[:i])]

# Driver code
lst = [(1, 2), (5, 7), (3, 6), (1, 2)]
print(removeDuplicates(lst))
```

**Output:**

```
[[1, 2], [5, 7], [3, 6]]

```