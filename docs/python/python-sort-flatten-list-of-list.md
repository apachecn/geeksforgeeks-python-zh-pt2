# Python |排序展平列表列表

> 原文:[https://www . geesforgeks . org/python-sort-flat-list-of-list/](https://www.geeksforgeeks.org/python-sort-flatten-list-of-list/)

列表列表的扁平化已经在前面讨论过了，但是有时候，除了扁平化之外，还需要以排序的方式获取字符串。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`sorted()` +列表理解**
这个想法类似于对列表的列表进行扁平化，但是除此之外，我们还添加了一个排序函数，对列表理解完成的返回的扁平化列表进行排序。

```
# Python3 code to demonstrate
# sort flatten list of list 
# using sorted + list comprehension

# initializing list of list 
test_list = [[3, 5], [7, 3, 9], [1, 12]]

# printing original list of list 
print("The original list : " + str(test_list))

# using sorted + list comprehension
# sort flatten list of list
res = sorted([j for i in test_list for j in i])

# print result
print("The sorted and flattened list : " + str(res))
```

**Output :**

```
The original list : [[3, 5], [7, 3, 9], [1, 12]]
The sorted and flattened list : [1, 3, 3, 5, 7, 9, 12]

```