# Python | Zip 不同大小列表

> 原文:[https://www . geesforgeks . org/python-zip-大小不同-list/](https://www.geeksforgeeks.org/python-zip-different-sized-list/)

在 Python 中，zipping 是一个实用工具，我们可以将一个列表与另一个列表配对。通常，只有当要压缩的两个列表的大小相同时，此任务才会成功。但有时我们要求不同大小的列表也要压缩。让我们讨论一下如果这个问题发生了，解决它的某些方法。

**方法#1:使用`enumerate()` +循环**
这是我们使用蛮力方法完成这个特殊任务的方式。在这个过程中，我们循环列表，当一个列表变得比另一个列表大时，我们循环元素，从头开始。

```
# Python3 code to demonstrate 
# zipping of two different size list 
# using enumerate() + loop

# initializing lists
test_list1 = [7, 8, 4, 5, 9, 10]
test_list2 = [1, 5, 6]

# printing original lists
print ("The original list 1 is : " + str(test_list1))
print ("The original list 2 is : " + str(test_list2))

# using enumerate() + loop
# zipping of two different size list 
res = []
for i, j in enumerate(test_list1):
    res.append((j, test_list2[i % len(test_list2)]))

# printing result 
print ("The zipped list is : " +  str(res))
```

**Output:**

```
The original list 1 is : [7, 8, 4, 5, 9, 10]
The original list 2 is : [1, 5, 6]
The zipped list is : [(7, 1), (8, 5), (4, 6), (5, 1), (9, 5), (10, 6)]

```

**方法 2:使用`itertools.cycle()`**
这是执行这个特定任务的另一种方式，在这种情况下，我们循环较小的列表，以便它可以从头开始压缩，以防较小的列表使用压缩功能耗尽。

```
# Python3 code to demonstrate 
# zipping of two different size list 
# using itertools.cycle()
from itertools import cycle

# initializing lists
test_list1 = [7, 8, 4, 5, 9, 10]
test_list2 = [1, 5, 6]

# printing original lists
print ("The original list 1 is : " + str(test_list1))
print ("The original list 2 is : " + str(test_list2))

# using itertools.cycle()
# zipping of two different size list 
res = list(zip(test_list1, cycle(test_list2))
            if len(test_list1) > len(test_list2)
            else zip(cycle(test_list1), test_list2))

# printing result 
print ("The zipped list is : " +  str(res))
```

**Output:**

```
The original list 1 is : [7, 8, 4, 5, 9, 10]
The original list 2 is : [1, 5, 6]
The zipped list is : [(7, 1), (8, 5), (4, 6), (5, 1), (9, 5), (10, 6)]

```