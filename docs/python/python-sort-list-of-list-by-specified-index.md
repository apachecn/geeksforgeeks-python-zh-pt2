# Python |按指定索引对列表进行排序

> 原文:[https://www . geesforgeks . org/python-sort-list-of-list-by-specified-index/](https://www.geeksforgeeks.org/python-sort-list-of-list-by-specified-index/)

我们可以使用传统的排序函数对列表进行排序。这将按照列表的第一个索引对列表进行排序。但更多的情况是，除了第一种情况，还需要通过其他索引元素对列表进行排序。让我们讨论执行这项任务的某些方法。

**方法#1:使用 `sort()` + lambda**
`sort()`可以通过传递一个函数作为关键字来执行这种变化的排序，该函数根据所需的内部列表索引执行排序。

```
# Python 3 code to demonstrate 
# to sort list of list by given index 
# using sort() + lambda

# initializing list 
test_list = [['Rash', 4, 28], ['Varsha', 2, 20], ['Nikhil', 1, 20], ['Akshat', 3, 21]]

# printing original list 
print ("The original list is : " + str(test_list))

# using sort() + lambda
# to sort list of list 
# sort by second index
test_list.sort(key = lambda test_list: test_list[1])

# printing result
print ("List after sorting by 2nd element of lists : " + str(test_list))
```

**输出:**

```
The original list is : [['Rash', 4, 28], ['Varsha', 2, 20], ['Nikhil', 1, 20], ['Akshat', 3, 21]]
List after sorting by 2nd element of lists : [['Nikhil', 1, 20], ['Varsha', 2, 20], ['Akshat', 3, 21], ['Rash', 4, 28]]

```

**方法 2:使用`sorted() + itemgetter()`**
这也可以应用于执行这个特定的任务。它的优点是不修改原始列表。`itemgetter()`用于获取需要执行排序操作的索引元素。

```
# Python3 code to demonstrate 
# to sort list of list by given index 
# using sorted() + itemgetter()
from operator import itemgetter

# initializing list 
test_list = [['Rash', 4, 28], ['Varsha', 2, 20], ['Nikhil', 1, 20], ['Akshat', 3, 21]]

# printing original list 
print ("The original list is : " + str(test_list))

# using sort() + lambda
# to sort list of list 
# sort by second index
res = sorted(test_list, key = itemgetter(1))

# printing result
print ("List after sorting by 2nd element of lists : " + str(res))
```

**输出:**

```
The original list is : [['Rash', 4, 28], ['Varsha', 2, 20], ['Nikhil', 1, 20], ['Akshat', 3, 21]]
List after sorting by 2nd element of lists : [['Nikhil', 1, 20], ['Varsha', 2, 20], ['Akshat', 3, 21], ['Rash', 4, 28]]

```