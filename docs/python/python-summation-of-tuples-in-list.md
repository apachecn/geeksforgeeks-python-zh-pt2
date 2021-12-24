# Python |列表中元组的求和

> 原文:[https://www . geesforgeks . org/python-列表中元组求和/](https://www.geeksforgeeks.org/python-summation-of-tuples-in-list/)

有时，在处理记录时，我们会遇到一个问题，即我们需要找到元组中存在的所有值的累积和。这可以应用于我们处理大量记录数据的情况。让我们讨论一下解决这个问题的某些方法。
**方法#1:使用 sum() + map()**
上述函数的组合可以用来解决这个特定的问题。在这种情况下，求和任务由 sum()执行，将求和功能应用于元组列表中的每个元素由 map()执行。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Summation of tuples in list
# using sum() + map()

# initialize list of tuple
test_list = [(1, 3), (5, 6, 7), (2, 6)]

# printing original tuples list
print("The original list : " + str(test_list))

# Summation of tuples in list
# using sum() + map()
res = sum(map(sum, test_list))

# printing result
print("The summation of all tuple elements are : " + str(res))
```

**Output : **

```
The original list : [(1, 3), (5, 6, 7), (2, 6)]
The summation of all tuple elements are : 30
```

**方法#2:使用 sum() + izip()**
以上功能的组合可以用来执行这个特定的任务。在本文中，我们使用 izip()执行 map()的任务。它有助于将求和的所有元素加在一起()。仅适用于单元素元组，并且仅适用于 Python2。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Summation of tuples in list
# using sum() + izip()
from itertools import izip

# initialize list of tuple
test_list = [(1, ), (5, ), (2, )]

# printing original tuples list
print("The original list : " + str(test_list))

# Summation of tuples in list
# using sum() + map()
res = sum(*izip(*test_list))

# printing result
print("The summation of all tuple elements are : " + str(res))
```

**Output : **

```
The original list : [(1, ), (5, ), (2, )]
The summation of all tuple elements are : 8
```