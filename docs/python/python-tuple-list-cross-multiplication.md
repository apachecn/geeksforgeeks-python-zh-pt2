# Python | Tuple 列表交叉乘法

> 原文:[https://www . geesforgeks . org/python-tuple-list-交叉乘法/](https://www.geeksforgeeks.org/python-tuple-list-cross-multiplication/)

有时，在处理 Python 记录时，我们会遇到一个问题，需要对元组列表执行交叉乘法。这种应用在 web 开发领域非常流行。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `zip()`**
上述功能的组合可用于执行该特定任务。在本文中，我们使用列表理解来遍历列表，并且在 zip()的帮助下执行跨列表的乘法运算。

```py
# Python3 code to demonstrate working of
# Tuple list cross multiplication
# using list comprehension + zip()

# initialize lists
test_list1 = [(2, 4), (6, 7), (5, 1)]
test_list2 = [(5, 4), (8, 10), (8, 14)]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# Tuple list cross multiplication
# using list comprehension + zip()
res = [(x[0] * y[0], x[1] * y[1]) for x, y in zip(test_list1, test_list2)]

# printing result
print("The multiplication across lists is : " + str(res))
```

**Output :**

```py
The original list 1 : [(2, 4), (6, 7), (5, 1)]
The original list 2 : [(5, 4), (8, 10), (8, 14)]
The multiplication across lists is : [(10, 16), (48, 70), (40, 14)]

```