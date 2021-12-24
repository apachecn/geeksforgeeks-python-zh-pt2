# Python | 0 和 1 交替的列表初始化

> 原文:[https://www . geesforgeks . org/python-list-initialize-with-alternate-0s-and-1s/](https://www.geeksforgeeks.org/python-list-initialization-with-alternate-0s-and-1s/)

单个数列表的初始化是一个通用问题，它的解决方案已经被讨论了很多次。但是有时我们需要用重复 K 次的元素初始化列表。这在需要在列表中预设数据的机器学习或人工智能算法中有使用案例。让我们讨论解决这个问题的某些方法。

**方法#1:使用列表理解**
在该方法中，我们针对每个元素出现的具体次数在列表中交替插入元素。它将元素的两次出现的计数总和的余数与元素的特定出现进行循环计算。

```py
# Python3 code to demonstrate 
# to perform cyclic initialization
# using list comprehension

# count of 1 
count_1 = 4

# count of 0
count_0 = 3

# total length of list 
size = 14

# initializing list cyclically
# using list comprehension
test_list =  [ 1 if i % (count_1 + count_0) < count_1 
                 else 0 for i in range(size) ]

# printing list after change
print ("The list after initializing : " + str(test_list))
```

**Output:**

```py
The list after initializing : [1, 1, 1, 1, 0, 0, 0, 1, 1, 1, 1, 0, 0, 0]

```

**方法 2:使用`itertools.cycle() + itertools.islice()`**
这是我们可以执行循环初始化的最 pythonic 化的方式。使用`cycle` 功能以循环方式将列表的每个部分分割成分配的元素大小。

```py
# Python3 code to demonstrate 
# to perform cyclic initialization
# using itertools.cycle() + itertools.islice()
import itertools

# count of 1 
count_1 = 4

# count of 0
count_0 = 3

# total length of list 
size = 16

# getting pattern
pattern = [1] * count_1 + [0] * count_0

# initializing list cyclically
# using itertools.cycle() + itertools.islice()
test_list = list(itertools.islice(itertools.cycle(pattern), size))

# printing list after change
print ("The list after initializing : " + str(test_list))
```

**Output:**

```py
The list after initializing : [1, 1, 1, 1, 0, 0, 0, 1, 1, 1, 1, 0, 0, 0, 1, 1]

```