# Python |查找列表长度的方法

> 原文:[https://www . geesforgeks . org/python-查找方法-列表长度/](https://www.geeksforgeeks.org/python-ways-to-find-length-of-list/)

列表是 python 日常编程不可或缺的一部分，所有 Python 用户都必须学习，了解它的实用性和操作是必不可少的，而且永远是一个优势。因此，本文讨论了这样一种在列表中查找元素数量的实用程序。

**方法 1:天真法**

在这种方法中，只需运行一个循环并增加计数器，直到列表的最后一个元素知道它的计数。这是在没有其他现有技术的情况下可能采用的最基本的策略。

**代码#1 :** 演示使用天真方法查找列表长度

```py
# Python code to demonstrate
# length of list
# using naive method

# Initializing list 
test_list = [ 1, 4, 5, 7, 8 ]

# Printing test_list
print ("The list is : " + str(test_list))

# Finding length of list 
# using loop
# Initializing counter
counter = 0
for i in test_list:

    # incrementing counter
    counter = counter + 1

# Printing length of list 
print ("Length of list using naive method is : " + str(counter))
```

**输出:**

```py
The list is : [1, 4, 5, 7, 8]
Length of list using naive method is : 5

```

**方法二:使用`len()`**

`len()`方法提供了最常用和最简单的方法来查找任何列表的长度。这是当今所有程序员采用的最传统的技术。

```py
# Python program to demonstrate working
# of len()
a = []
a.append("Hello")
a.append("Geeks")
a.append("For")
a.append("Geeks")
print("The length of list is: ", len(a))
```

**Output:**

```py
The length of list is:  4

```

```py
# Python program to demonstrate working
# of len()
n = len([10, 20, 30])
print("The length of list is: ", n)
```

**Output:**

```py
The length of list is:  3

```

**方法三:使用`length_hint()`**

这种技术是一种不太为人所知的查找列表长度的技术。这个特殊的方法是在操作类中定义的，它还可以告诉列表中存在的元素的数量。

**代码#2 :** 演示使用`len()`和`length_hint()`查找列表长度

```py
# Python code to demonstrate
# length of list
# using len() and length_hint
from operator import length_hint

# Initializing list 
test_list = [ 1, 4, 5, 7, 8 ]

# Printing test_list
print ("The list is : " + str(test_list))

# Finding length of list 
# using len()
list_len = len(test_list)

# Finding length of list 
# using length_hint()
list_len_hint = length_hint(test_list)

# Printing length of list 
print ("Length of list using len() is : " + str(list_len))
print ("Length of list using length_hint() is : " + str(list_len_hint))
```

**输出:**

```py
The list is : [1, 4, 5, 7, 8]
Length of list using len() is : 5
Length of list using length_hint() is : 5

```

**性能分析–天真 vs `len()` vs `length_hint()`**

当在选项中选择时，总是有必要有一个合理的理由为什么选择一个而不是另一个。本节对执行所有这些命令所需的时间进行了时间分析，以提供更好的使用选择。

**代码#3 :** 性能分析

```py
# Python code to demonstrate
# length of list
# Performance Analysis
from operator import length_hint
import time

# Initializing list 
test_list = [ 1, 4, 5, 7, 8 ]

# Printing test_list
print ("The list is : " + str(test_list))

# Finding length of list 
# using loop
# Initializing counter
start_time_naive = time.time()
counter = 0
for i in test_list:

    # incrementing counter
    counter = counter + 1
end_time_naive = str(time.time() - start_time_naive)

# Finding length of list 
# using len()
start_time_len = time.time()
list_len = len(test_list)
end_time_len = str(time.time() - start_time_len)

# Finding length of list 
# using length_hint()
start_time_hint = time.time()
list_len_hint = length_hint(test_list)
end_time_hint = str(time.time() - start_time_hint)

# Printing Times of each 
print ("Time taken using naive method is : " + end_time_naive)
print ("Time taken using len() is : " + end_time_len)
print ("Time taken using length_hint() is : " + end_time_hint)
```

**输出:**

```py
The list is : [1, 4, 5, 7, 8]
Time taken using naive method is : 2.6226043701171875e-06
Time taken using len() is : 1.1920928955078125e-06
Time taken using length_hint() is : 1.430511474609375e-06

```

**结论:**可以清楚的看到，所花费的时间是**天真的> > `length_hint()` > len()** ，因此`len()`是最佳的使用选择。