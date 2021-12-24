# Python |缩小重复元素的给定列表

> 原文:[https://www . geeksforgeeks . org/python-为重复元素收缩给定列表/](https://www.geeksforgeeks.org/python-shrink-given-list-for-repeating-elements/)

给定一个重复元素的列表，编写一个 python 程序来缩小元素的重复，并将重复转换为包含重复元素及其重复次数的列表的元组元素，从而将给定的列表转换为元组列表。

**示例:**

```
Input : [1, 1, 1, 2, 3, 3, 3, 4, 4, 4, 4]
Output : [(1, 3), (2, 1), (3, 3), (4, 4)]

Input : ['alice', 'alice', 'bob']
Output : [('alice', 2), ('bob', 1)]

```

**方法#1 :** 蛮力
为了缩小列表，这是一个幼稚的方法。它需要另一个列表，比如“tup_list”。将索引初始化为 0，并使用循环来检查列表中每个唯一元素的重复次数。找到元素及其重复计数后，以元组的形式将其追加到列表中。

```
# Python3 program to Shrink list 
# for repeating elements

def shrinkList(lst):
    tup_list = []
    i, index = 0, 0
    while(index < len(lst)):
        element_count = 0
        while(i < len(lst) and lst[i] == lst[index]):
            element_count += 1
            i += 1
        tup_list.append((lst[index], element_count))
        index += element_count

    return tup_list

# Driver Code
lst = [1, 1, 1, 2, 2, 3, 3, 4]
print(shrinkList(lst))
```

**Output:**

```
[(1, 3), (2, 2), (3, 2), (4, 1)]

```

**方法#2 :** 交替蛮力
这是另一种蛮力方法，用于循环遍历列表。它使用变量“prev_element”来存储前一个元素。首先，它检查这是否是第一个唯一的元素，如果是，它递增计数器并将该元素存储到 prev_element。如果元素重复，只需增加计数器。如果所有这些情况都不成立，那么只需将 prev_element 作为元组添加到 tup_list 中。

```
# Python3 program to Shrink list 
# for repeating elements

def shrinkList(lst):
    prev_element = None
    count = 0
    tup_list = []

    for ele in lst:
        if (prev_element == ele): 
            count += 1

        elif (prev_element is None):
            count += 1
            prev_element = ele

        else:
            tup_list.append((prev_element, count))
            count = 1
            prev_element = ele

    tup_list.append((prev_element, count))
    return tup_list

# Driver Code
lst = [1, 1, 1, 2, 2, 3, 3, 4]
print(shrinkList(lst))
```

**Output:**

```
[(1, 3), (2, 2), (3, 2), (4, 1)]

```

**方法#3 :** 使用 Itertools.groupby()
这是一种解决给定问题的更精确的方法。`itertools.groupby()`做一个迭代器，从可迭代中返回连续的键和组。它将相似的元素分组，并将元素及其计数作为元组列表返回。

```
# Python3 program to Shrink list 
# for repeating elements
from itertools import groupby

def shrinkList(lst):
    return ([(element, len(list(i)))
    for element, i in groupby(lst)])

# Driver Code
lst = [1, 1, 1, 2, 2, 3, 3, 4]
print(shrinkList(lst))
```

**Output:**

```
[(1, 3), (2, 2), (3, 2), (4, 1)]

```