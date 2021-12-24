# Python |连续子列表的平均值

> 原文:[https://www . geesforgeks . org/python-mean-of-continuous-sublist/](https://www.geeksforgeeks.org/python-mean-of-consecutive-sublist/)

编程领域的一些经典问题来自不同的类别，其中之一就是求子集的平均值。当我们需要计算平均值并存储连续组平均值时，这个特殊问题也很常见。让我们用 python 语言尝试不同的方法来解决这个问题。

**方法#1:使用列表理解+ `sum()`**
可以使用列表理解来执行这个特定的任务，以过滤出连续的组，并且可以使用求和函数来获得过滤后的解的总和。我们将总和除以子列表大小作为平均值。

```py
# Python3 code to demonstrate
# Mean of consecutive Sublist
# using list comprehension + sum()

# initializing list
test_list = [4, 7, 8, 10, 12, 15, 13, 17, 14]

# printing original list 
print("The original list : " + str(test_list))

# using list comprehension + sum()
# Mean of consecutive Sublist
res = [ sum(test_list[x : x + 3]) / 3 for x in range(0, len(test_list), 3)]

# printing result
print("The grouped average list is : " + str(res))
```

**Output :**

```py
The original list : [4, 7, 8, 10, 12, 15, 13, 17, 14]
The grouped average list is : [6.333333333333333, 12.333333333333334, 14.666666666666666]

```