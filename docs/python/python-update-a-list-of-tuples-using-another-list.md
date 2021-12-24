# Python |使用另一个列表更新元组列表

> 原文:[https://www . geesforgeks . org/python-update-一个元组列表-使用另一个列表/](https://www.geeksforgeeks.org/python-update-a-list-of-tuples-using-another-list/)

给定两个元组列表，编写一个 Python 程序根据“list2”更新“list1”，并返回更新后的列表。

**示例:**

```py
Input : list1 = [('x', 0), ('y', 5)]
        list2 = [('x', 100), ('y', 200)]
Output : [('x', 100), ('y', 200)]

Input : list1 = [('a', 0), ('b', 0), ('c', 0)]
        list2 = [('a', 1), ('b', 2)]
Output :[('a', 1), ('b', 2), ('c', 0)]

```

**进场#1** 皮托尼天真
这是皮托尼天真的进场。我们只需将元组列表转换成字典，然后用*列表 2* 更新它，并将字典转换回列表。

```py
# Python3 code to Update a list 
# of tuples according to another list

def merge(list1, list2): 
    dic = dict(list1)
    dic.update(dict(list2))
    return list(dic.items())

# Driver Code
list1 = [('a', 0), ('b', 0), ('c', 0)]
list2 = [('a', 5), ('c', 3)]
print(merge(list1, list2))
```

**Output:**

```py
[('a', 5), ('b', 0), ('c', 3)]

```

**方法#2** 使用 *defaultdict*
Python 集合模块提供了 *defaultdict()* 方法，该方法使用该方法。首先，我们用 defaultdict 方法初始化“dic ”,将列表作为工厂传递。使用循环将每个元组的左元素作为键追加，将每个元组的右元素作为值追加到两个列表中。现在只需使用排序函数，以这样一种方式生成列表:对于每个唯一键，它保持元组右元素的最大值。

```py
# Python3 code to Update a list 
# of tuples according to another list

from collections import defaultdict

def merge(list1, list2): 
    dic = defaultdict(list)
    for i, j in list1 + list2:
        dic[i].append(j)

    return sorted([(i, max(j)) for i, j in dic.items()],
    key = lambda x:x[0])

# Driver Code
list1 = [('a', 0), ('b', 0), ('c', 0)]
list2 = [('a', 5), ('c', 3)]
print(merge(list1, list2))
```

**Output:**

```py
[('a', 5), ('b', 0), ('c', 3)]

```