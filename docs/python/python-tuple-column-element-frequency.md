# Python | Tuple 列元素频率

> 原文:[https://www . geesforgeks . org/python-tuple-column-element-frequency/](https://www.geeksforgeeks.org/python-tuple-column-element-frequency/)

在 python 中，我们需要处理各种形式的数据，其中之一是元组列表，我们可能需要在其中执行任何类型的操作。这篇特别的文章讨论了在元组列表中查找 Kth 元素的频率的方法。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`map() + count()`**
map 函数可以用来累加列表中所有元组的索引，计数频率的任务可以使用 python 库的泛型计数函数来完成。

```py
# Python3 code to demonstrate
# Tuple Column element frequency
# using map() + count()

# initializing list of tuples
test_list = [(1, 'Geeks'), (2, 'for'), (3, 'Geeks')]

# printing the original list
print ("The original list is : " + str(test_list))

# initializing K 
K = 1

# using map() + count()
# Tuple Column element frequency
res = list(map(lambda i : i[K], test_list)).count('Geeks')

# printing result
print ("The frequency of element at Kth index is : " + str(res))
```

**Output :**

```py
The original list is : [(1, 'Geeks'), (2, 'for'), (3, 'Geeks')]
The frequency of element at Kth index is : 2

```