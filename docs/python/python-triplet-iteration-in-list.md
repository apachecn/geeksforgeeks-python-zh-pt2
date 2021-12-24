# Python |列表中的三元组迭代

> 原文:[https://www . geesforgeks . org/python-三元组-迭代在列表中/](https://www.geeksforgeeks.org/python-triplet-iteration-in-list/)

列表迭代在编程中很常见，但有时需要以连续的三元组打印元素。这个特殊的问题很常见，有一个解决方案总是很方便。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用列表理解**
列表理解可以通过访问列表中的当前、下一个和下一个元素，然后打印它们来打印三元组。在将最后一个元素与第一个元素配对以形成循环三元组对时必须小心。

```
# Python3 code to demonstrate 
# Triplet iteration in List
# using list comprehension
from itertools import compress

# initializing list 
test_list = [0, 1, 2, 3, 4, 5]

# printing original list
print ("The original list is : " + str(test_list))

# using list comprehension
# Triplet iteration in List
res = [((i), (i + 1) % len(test_list), (i + 2) % len(test_list)) 
                                 for i in range(len(test_list))]

# printing result
print ("The triplet list is : " + str(res))
```

**Output :**

```
The original list is : [0, 1, 2, 3, 4, 5]
The triplet list is : [(0, 1, 2), (1, 2, 3), (2, 3, 4), (3, 4, 5), (4, 5, 0), (5, 0, 1)]

```