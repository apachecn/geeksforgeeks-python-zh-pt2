# Python |元组列表最小值

> 原文:[https://www . geesforgeks . org/python-元组列表-最小值/](https://www.geeksforgeeks.org/python-list-of-tuples-minimum/)

有时，在处理 Python 记录时，我们可能会遇到一个问题，即我们需要执行元组列表的交叉最小化。这种应用在 web 开发领域非常流行。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `zip() + min()`**
上述功能的组合可用于执行该特定任务。在本文中，我们使用列表理解对列表进行迭代，并在 zip()的帮助下执行跨列表的最小化。最小值使用 min()执行。

```
# Python3 code to demonstrate working of
# List of tuples Minimum
# using list comprehension + zip() + min()

# initialize lists
test_list1 = [(2, 4), (6, 7), (5, 1)]
test_list2 = [(5, 4), (8, 10), (8, 14)]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# List of tuples Minimum
# using list comprehension + zip() + min()
res = [(min(x[0], y[0]), min(x[1], y[1])) for x, y in zip(test_list1, test_list2)]

# printing result
print("The Minimum across lists is : " + str(res))
```

**Output :**

```
The original list 1 : [(2, 4), (6, 7), (5, 1)]
The original list 2 : [(5, 4), (8, 10), (8, 14)]
The Minimum across lists is : [(2, 4), (6, 7), (5, 1)]

```