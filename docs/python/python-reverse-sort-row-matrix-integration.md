# Python |反向排序行矩阵集成

> 原文:[https://www . geesforgeks . org/python-反向-排序-行-矩阵-集成/](https://www.geeksforgeeks.org/python-reverse-sort-row-matrix-integration/)

在解决问题的过程中，我们经常会遇到许多需要对列表进行反向排序的问题。但有时我们也希望对另一个列表进行反向排序，这样的话，的元素会自动移位，并保持在与第一个列表相同的索引处，即使在第一个列表进行反向排序之后也是如此。让我们讨论一下实现这一点的某些方法。

**方法一:使用`sorted() + reverse + zip() + itemgetter()`**
结合这三个功能，我们有可能完成任务。zip 函数将两个列表绑定在一起，sorted 函数对列表进行排序，itemgetter 函数用于定义我们需要第二个列表移动的指标，在本例中是第一个列表。反向排序由反向处理。

```py
# Python3 code to demonstrate 
# Reverse Sort Row Matrix integration
# using sorted() + zip() + itemgetter()
from operator import itemgetter

# initializing lists
test_list1 = [3, 4, 9, 1, 6]
test_list2 = [1, 5, 3, 6, 7]

# printing original lists
print ("The original list 1 is : " + str(test_list1))
print ("The original list 2 is : " + str(test_list2))

# using sorted() + zip() + itemgetter()
# Reverse Sort Row Matrix integration
res = [list(x) for x in zip(*sorted(zip(test_list1, test_list2), key = itemgetter(0), reverse = True))]

# printing result 
print ("The lists after integrity reverse sort : " + str(res))
```

**Output :**

```py
The original list 1 is : [3, 4, 9, 1, 6]
The original list 2 is : [1, 5, 3, 6, 7]
The lists after integrity reverse sort : [[9, 6, 4, 3, 1], [3, 7, 5, 1, 6]]

```