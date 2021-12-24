# Python |将重复项合并到列表中

> 原文:[https://www . geesforgeks . org/python-合并-复制到列表中/](https://www.geeksforgeeks.org/python-merging-duplicates-to-list-of-list/)

有时，我们需要执行常规任务，将一些相似的元素分组到一个单独的列表中，从而形成一个列表列表。这也有助于计数，并获得元素的排序顺序。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`collections.Counter()`**
这个特殊的函数可以证明对执行这个特殊的任务非常有用，因为它计算列表中元素的频率，然后我们可以使用列表理解将它们配对。

```py
# Python3 code to demonstrate
# grouping like elements as list 
# using collections.Counter()
import collections

# initializing list 
test_list = [1, 3, 4, 2, 1, 3, 4, 2, 3, 4, 1]

# printing original list 
print("The original list : " + str(test_list))

# using collections.Counter()
# grouping like elements as list 
temp = collections.Counter(test_list)
res = [[i] * j for i, j in temp.items()]

# print result
print("The elements after grouping are : " + str(res))
```

**Output :**

```py
The original list : [1, 3, 4, 2, 1, 3, 4, 2, 3, 4, 1]
The elements after grouping are : [[1, 1, 1], [2, 2], [3, 3, 3], [4, 4, 4]]

```