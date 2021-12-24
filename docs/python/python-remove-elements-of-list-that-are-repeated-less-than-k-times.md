# Python |移除列表中重复次数小于 k 次的元素

> 原文:[https://www . geesforgeks . org/python-移除重复次数少于 k 次的列表元素/](https://www.geeksforgeeks.org/python-remove-elements-of-list-that-are-repeated-less-than-k-times/)

给定一个整数列表(元素可以重复)，编写一个 Python 程序来移除重复次数少于 k 次的元素。

**示例:**

```
Input : lst = ['a', 'a', 'a', 'b', 'b', 'c'], k = 2
Output : ['a', 'a', 'a', 'b', 'b']

Input : lst = [1, 1, 1, 1, 2, 2, 3, 3, 3, 4, 4], k = 3
Output : [1, 1, 1, 1, 3, 3, 3]

```

**方法#1 :** 皮托尼天真

从`collections module`开始`Counter()`构建一个将值映射到计数的字典，并将它们保存在“计数”中。然后我们使用“temp_lst”来存储需要移除的元素。最后，我们遍历给定的列表，并将所有不在“temp_lst”中的元素追加到包含所需输出的“res_lst”中。

```
# Python3 program to Remove elements of 
# list that repeated less than k times
from collections import Counter

def removeElements(lst, k):
    counted = Counter(lst)

    temp_lst = []
    for el in counted:
        if counted[el] < k:
            temp_lst.append(el)

    res_lst = []
    for el in lst:
        if el not in temp_lst:
            res_lst.append(el)

    return(res_lst)

# Driver code
lst = ['a', 'a', 'a', 'b', 'b', 'c']
k = 2
print(removeElements(lst, k))
```

**Output:**

```
['a', 'a', 'a', 'b', 'b']

```

**方法#2 :** 有效方法

使用*计数器*方法的有效方法是构建一个将值映射到计数的字典，然后使用列表理解来过滤大于指定值的计数。这种方法在时间和空间上都很有效。

```
# Python3 program to Remove elements of 
# list that repeated less than k times
from collections import Counter

def removeElements(lst, k):
    counted = Counter(lst)
    return [el for el in lst if counted[el] >= k]

# Driver code
lst = ['a', 'a', 'a', 'b', 'b', 'c']
k = 2
print(removeElements(lst, k))
```

**Output:**

```
['a', 'a', 'a', 'b', 'b']

```