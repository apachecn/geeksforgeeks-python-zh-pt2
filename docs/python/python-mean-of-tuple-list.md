# Python |元组列表平均值

> 原文:[https://www.geeksforgeeks.org/python-mean-of-tuple-list/](https://www.geeksforgeeks.org/python-mean-of-tuple-list/)

有时，在使用 Python 元组列表时，我们可能会遇到一个问题，即我们需要找到列表中元组值的平均值。这个问题在包括数学在内的许多领域都有可能应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
可以想到的解决这个问题的第一种方法可以是蛮力方法，我们只需循环每个元组来添加元素，然后只需将其除以列表中元组的数量。

```
# Python3 code to demonstrate working of
# Mean of tuple list
# Using loops

# Initializing list
test_list = [(1, 4, 5), (7, 8), (2, 4, 10)]

# printing original list
print("The original list is : " + str(test_list))

# Average of tuple list
# Using loops
sum = 0
for sub in test_list:
    for i in sub:
        sum = sum + i
res = sum / len(test_list)

# printing result
print("The mean of tuple list is : " + str(res))
```

**Output :**

```
The original list is : [(1, 4, 5), (7, 8), (2, 4, 10)]
The mean of tuple list is : 13.666666666666666

```