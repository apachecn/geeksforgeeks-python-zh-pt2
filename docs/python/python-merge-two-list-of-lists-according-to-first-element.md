# Python |根据第一个元素

合并两个列表列表

> 原文:[https://www . geesforgeks . org/python-merge-two-list-list-根据第一个元素/](https://www.geeksforgeeks.org/python-merge-two-list-of-lists-according-to-first-element/)

给定两个长度相等的列表，根据每个子列表的第一个公共元素，编写一个 Python 程序来合并给定的两个列表。

**示例:**

```
Input : lst1 = [[1, 'Alice'], [2, 'Bob'], [3, 'Cara']]
        lst2 = [[1, 'Delhi'], [2, 'Mumbai'], [3, 'Chennai']]
Output : [[1, 'Alice', 'Delhi'], [2, 'Bob', 'Mumbai'], [3, 'Cara', 'Chennai']]

Input : lst1 = [ ['c', 'class'], ['g', 'greek'], ]
        lst2 = [['c', 'coder'], ['g', 'god'], ]
Output : [['c', 'class', 'coder'], ['g', 'greek', 'god']]

```

**方法#1 :** Python *zip()* 带列表理解

```
# Python3 program to Merge two list of 
# lists according to first element

def merge(lst1, lst2):
    return [a + [b[1]] for (a, b) in zip(lst1, lst2)]

# Driver code
lst1 = [[1, 'Alice'], [2, 'Bob'], [3, 'Cara']]
lst2 = [[1, 'Delhi'], [2, 'Mumbai'], [3, 'Chennai']]
print(merge(lst1, lst2))
```

**Output:**

```
[[1, 'Alice', 'Delhi'], [2, 'Bob', 'Mumbai'], [3, 'Cara', 'Chennai']]

```

**方法二:** Python *枚举()*带列表理解

```
# Python3 program to Merge two list of 
# lists according to first element
import collections

def merge(lst1, lst2):
    return [(sub + [lst2[i][-1]]) for i, sub in enumerate(lst1)]

# Driver code
lst1 = [[1, 'Alice'], [2, 'Bob'], [3, 'Cara']]
lst2 = [[1, 'Delhi'], [2, 'Mumbai'], [3, 'Chennai']]
print(merge(lst1, lst2))
```

**Output:**

```
[[1, 'Alice', 'Delhi'], [2, 'Bob', 'Mumbai'], [3, 'Cara', 'Chennai']]

```

**方法#3 :** Python 字典
在该方法中，我们用 *collections.defaultdict* 初始化‘dict 1’，遍历‘lst 1’+‘lst 2’，并将‘lst 1’的第一个元素作为键追加，并将两个子列表的第二个元素作为值进行组合。最后，我们遍历“dict1”并用期望的输出初始化“dictlist”。

```
# Python3 program to Merge two list of 
# lists according to first element
import collections

def merge(lst1, lst2):
    dict1 = collections.defaultdict(list)

    for e in lst1 + lst2:
        dict1[e[0]].append(e[1])
    dictlist = list()

    for key, value in dict1.items():
        dictlist.append([key]+value)

    return dictlist

# Driver code
lst1 = [[1, 'Alice'], [2, 'Bob'], [3, 'Cara']]
lst2 = [[1, 'Delhi'], [2, 'Mumbai'], [3, 'Chennai']]
print(merge(lst1, lst2))
```

**Output:**

```
[[1, 'Alice', 'Delhi'], [2, 'Bob', 'Mumbai'], [3, 'Cara', 'Chennai']]

```