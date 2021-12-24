# Python–用其他列表中的元素替换索引元素

> 原文:[https://www . geesforgeks . org/python-replace-index-elements-with-elements-in-other-list/](https://www.geeksforgeeks.org/python-replace-index-elements-with-elements-in-other-list/)

有时，在使用 Python 数据时，我们可能会遇到一个问题，即我们有两个列表，我们需要用其他列表中的实际元素替换一个列表中的位置。让我们讨论执行这项任务的某些方法。

**方法一:利用列表理解**
这是解决这个问题的一种方法。在这种情况下，我们只需遍历列表，并将索引值从一个列表分配给另一个列表。

```py
# Python3 code to demonstrate 
# Replace index elements with elements in Other List
# using list comprehension

# Initializing lists
test_list1 = ['Gfg', 'is', 'best']
test_list2 = [0, 1, 2, 1, 0, 0, 0, 2, 1, 1, 2, 0]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Replace index elements with elements in Other List
# using list comprehension
res = [test_list1[idx] for idx in test_list2]

# printing result 
print ("The lists after index elements replacements is : " + str(res))
```

**Output :**

> 原始列表 1 为:['Gfg '，' is '，' best']
> 原始列表 2 为:[0，1，2，1，0，0，0，2，1，1，2，0]
> 索引元素替换后的列表为:['Gfg '，' is '，' best '，' is '，' Gfg '，' Gfg '，' Gfg '，' best '，' is '，' best '，' Gfg']