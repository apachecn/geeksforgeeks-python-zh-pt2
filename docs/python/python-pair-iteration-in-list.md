# 列表中的 Python | Pair 迭代

> 原文:[https://www . geesforgeks . org/python-pair-iteration-in-list/](https://www.geeksforgeeks.org/python-pair-iteration-in-list/)

列表迭代在编程中很常见，但有时需要连续成对打印元素。这个特殊的问题很常见，有一个解决方案总是很方便。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用列表理解**
列表理解可以通过访问列表中的当前和下一个元素，然后打印它们来打印对。将最后一个元素与第一个元素配对以形成循环对时，必须小心。

```py
# Python3 code to demonstrate 
# pair iteration in list 
# using list comprehension
from itertools import compress

# initializing list  
test_list = [0, 1, 2, 3, 4, 5]

# printing original list
print ("The original list is : " + str(test_list))

# using list comprehension
# to perform pair iteration in list 
res = [((i), (i + 1) % len(test_list)) 
         for i in range(len(test_list))]

# printing result
print ("The pair list is : " + str(res))
```

**Output:**

```py
The original list is : [0, 1, 2, 3, 4, 5]
The pair list is : [(0, 1), (1, 2), (2, 3), (3, 4), (4, 5), (5, 0)]

```