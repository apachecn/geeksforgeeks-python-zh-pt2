# Python–元组中的多列排序

> 原文:[https://www . geesforgeks . org/python-多列-元组中排序/](https://www.geeksforgeeks.org/python-mutiple-column-sort-in-tuples/)

有时，在处理记录时，我们可能会遇到这样的问题:我们需要对其中一列执行排序操作，而对另一列(如果元素相等)执行相反的排序。这种问题可能会出现在许多领域，例如 web 开发。让我们讨论一下解决这个问题的某些方法。

> **输入** : test_list = [(6，7)，(6，5)，(6，4)，(7，10)]
> **输出** : [(7，10)，(6，4)，(6，5)，(6，7)]
> 
> **输入** : test_list = [(10，7)，(8，5)]
> **输出** : [(10，7)，(8，5)]

**方法#1:使用 sorted() + lambda**
上述函数的组合可以提供解决这个问题的方法之一。在本例中，我们使用 sorted()执行排序，顺序和列操作由 lambda 函数处理。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Multiple Column Sort in Tuples
# Using sorted() + lambda

# initializing list
test_list = [(6, 7), (6, 5), (1, 4), (8, 10)]

# printing original list
print("The original list is : " + str(test_list))

# Multiple Column Sort in Tuples
# Using sorted() + lambda
res = sorted(test_list, key = lambda sub: (-sub[0], sub[1]))

# printing result
print("The sorted records : " + str(res))
```

**Output : **

```py
The original list is : [(6, 7), (6, 5), (1, 4), (8, 10)]
The sorted records : [(8, 10), (6, 5), (6, 7), (1, 4)]
```

**方法#2:使用 itemgetter() + sorted()**
这是可以执行此任务的另一种方式。在本例中，我们使用 itemgetter()执行 lambda 函数所需的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Multiple Column Sort in Tuples
# Using itemgetter() + sorted()
from operator import itemgetter

# initializing list
test_list = [(6, 7), (6, 5), (1, 4), (8, 10)]

# printing original list
print("The original list is : " + str(test_list))

# Multiple Column Sort in Tuples
# Using itemgetter() + sorted()
res = sorted(test_list, key = itemgetter(1))
res = sorted(res, key = itemgetter(0), reverse = True)

# printing result
print("The sorted records : " + str(res))
```

**Output : **

```py
The original list is : [(6, 7), (6, 5), (1, 4), (8, 10)]
The sorted records : [(8, 10), (6, 5), (6, 7), (1, 4)]
```