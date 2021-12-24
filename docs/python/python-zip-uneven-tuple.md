# Python | Zip 不均匀元组

> 原文:[https://www.geeksforgeeks.org/python-zip-uneven-tuple/](https://www.geeksforgeeks.org/python-zip-uneven-tuple/)

在 python 中，zipping 是一个实用工具，我们可以将一条记录与另一条记录配对。通常，只有当要压缩的两个记录的大小相同时，此任务才会成功。但有时我们要求不同大小的记录也要压缩。让我们讨论一下如果这个问题发生了，解决它的某些方法。

**方法#1:使用`enumerate()` +循环**
这是我们使用蛮力方法完成这个特殊任务的方式。在这个过程中，我们循环元组，当一个变得比另一个大时，我们循环元素，从头开始。

```py
# Python3 code to demonstrate 
# Zip Uneven Tuple
# using enumerate() + loop

# initializing tuples
test_tup1 = (7, 8, 4, 5, 9, 10)
test_tup2 = (1, 5, 6)

# printing original tuples
print ("The original tuple 1 is : " + str(test_tup1))
print ("The original tuple 2 is : " + str(test_tup2))

# using enumerate() + loop
# Zip Uneven Tuple
res = []
for i, j in enumerate(test_tup1):
    res.append((j, test_tup2[i % len(test_tup2)]))

# printing result 
print ("The zipped tuple is : " + str(res))
```

**Output :**

```py
The original tuple 1 is : (7, 8, 4, 5, 9, 10)
The original tuple 2 is : (1, 5, 6)
The zipped tuple is : [(7, 1), (8, 5), (4, 6), (5, 1), (9, 5), (10, 6)]

```