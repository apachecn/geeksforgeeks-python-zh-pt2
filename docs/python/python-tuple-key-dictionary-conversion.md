# Python | Tuple 键字典转换

> 原文:[https://www . geesforgeks . org/python-tuple-key-dictionary-conversion/](https://www.geeksforgeeks.org/python-tuple-key-dictionary-conversion/)

用 Python 编码时总是需要相互转换，这也是因为 Python 作为数据科学领域主要语言的扩展。本文讨论了另一个问题，即转换为字典，将键作为第一对元素作为元组分配，将其余元素作为值分配。让我们讨论一下实现这一点的某些方法。

**方法#1:使用字典理解**
这个问题可以通过使用字典理解的速记来解决，该速记执行经典的朴素方法，即在字典中单行循环。

```py
# Python3 code to demonstrate
# Tuple key dictionary conversion
# using list comprehension

# initializing list
test_list = [('Nikhil', 21, 'JIIT'), ('Akash', 22, 'JIIT'), ('Akshat', 22, 'JIIT')]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension
# Tuple key dictionary conversion
res = {(sub[0], sub[1]): sub[2:] for sub in test_list}

# print result
print("The dictionary after conversion : " + str(res))
```

**Output :**

```py
The original list : [('Nikhil', 21, 'JIIT'), ('Akash', 22, 'JIIT'), ('Akshat', 22, 'JIIT')]
The dictionary after conversion : {('Akash', 22): ('JIIT', ), ('Akshat', 22): ('JIIT', ), ('Nikhil', 21): ('JIIT', )}

```