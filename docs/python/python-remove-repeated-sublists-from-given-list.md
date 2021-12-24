# Python |从给定列表中删除重复的子列表

> 原文:[https://www . geesforgeks . org/python-remove-repeated-sublist-from-给定列表/](https://www.geeksforgeeks.org/python-remove-repeated-sublists-from-given-list/)

给定一个列表列表，编写一个 Python 程序从给定列表中移除所有重复的子列表(顺序也不同)。

**示例:**

```py
Input : [[1], [1, 2], [3, 4, 5], [2, 1]]
Output : [[1], [1, 2], [3, 4, 5]]

Input : [['a'], ['x', 'y', 'z'],  ['m', 'n'], ['a'], ['m', 'n']]
Output : [['a'], ['x', 'y', 'z'], ['m', 'n']]

```

**进场#1 :** *集合*理解+拆箱

我们的第一种方法是用*排序的*元组来设置理解。在列表的每次迭代中，我们将当前的子列表转换为一个排序的元组，并返回所有这些元组的集合，这又消除了子列表的所有重复出现，从而移除了所有重复的重新排列的子列表。

```py
# Python3 program to Remove repeated 
# unordered sublists from list

def Remove(lst):
     return ([list(i) for i in {*[tuple(sorted(i)) for i in lst]}])  

# Driver code
lst = [[1], [1, 2], [3, 4, 5], [2, 1]]
print(Remove(lst))
```

**Output:**

```py
[[1, 2], [3, 4, 5], [1]]

```

**逼近#2 :** 使用*映射()*带*集*和*排序的*元组。

```py
# Python3 program to Remove repeated 
# unordered sublists from list

def Remove(lst):
     return list(map(list, (set(map(lambda x: tuple(sorted(x)), lst)))))

# Driver code
lst = [[1], [1, 2], [3, 4, 5], [2, 1]]
print(Remove(lst))
```

**Output:**

```py
[[1, 2], [3, 4, 5], [1]]

```

**维持秩序–**

**方法#3 :** 使用排序元组作为哈希

首先，我们将一个空列表初始化为“res”，将一个集合初始化为“check”。现在，对于列表中的每个子列表，将子列表转换为排序元组，并将其保存在“hsh”中。然后检查检查中是否存在 hsh。如果没有，则将当前子列表追加到“”。“res”和“hsh”改为“check”。这样更容易维护子列表的顺序。

```py
# Python3 program to Remove repeated 
# unordered sublists from list

def Remove(lst):
     res = []
     check = set()

     for x in lst:
         hsh = tuple(sorted(x))
         if hsh not in check:
             res.append(x)
             check.add(hsh)

     return res

# Driver code
lst = [[1], [1, 2], [3, 4, 5], [2, 1]]
print(Remove(lst))
```

**Output:**

```py
[[1], [1, 2], [3, 4, 5]]

```