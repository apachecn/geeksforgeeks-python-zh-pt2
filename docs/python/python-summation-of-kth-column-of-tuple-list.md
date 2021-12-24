# Python |元组列表第 k 列求和

> 原文:[https://www . geeksforgeeks . org/python-第 k 列元组列表求和/](https://www.geeksforgeeks.org/python-summation-of-kth-column-of-tuple-list/)

有时，在使用 Python 列表时，我们可能会有一个任务，其中我们需要使用元组列表，并获得其 Kth 索引的可能累积。当处理数据信息时，这个问题在 web 开发领域有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `sum()`**
该任务可以使用上述功能的组合来执行。在这种情况下，使用`sum()`进行索引求和，列表理解驱动列表中每个元组的第 N 个索引元素的迭代和访问。

```
# Python3 code to demonstrate working of
# Summation of Kth Column of Tuple List
# using list comprehension + sum()

# initialize list
test_list = [(5, 6, 7), (1, 3, 5), (8, 9, 19)]

# printing original list
print("The original list is : " + str(test_list))

# initialize K
K = 2

# Summation of Kth Column of Tuple List
# using list comprehension + sum()
res = sum([sub[K] for sub in test_list])

# printing result
print("Summation of Kth Column of Tuple List : " + str(res))
```

**Output :**

```
The original list is : [(5, 6, 7), (1, 3, 5), (8, 9, 19)]
Summation of Kth Column of Tuple List : 31

```