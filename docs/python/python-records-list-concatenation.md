# Python |记录列表串联

> 原文:[https://www . geesforgeks . org/python-records-list-concation/](https://www.geeksforgeeks.org/python-records-list-concatenation/)

有时，在处理 Python 记录时，我们可能会遇到一个问题，需要对元组列表执行交叉连接。这种应用在 web 开发领域非常流行。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `zip()`**
上述功能的组合可用于执行该特定任务。在本文中，我们使用列表理解来遍历列表，并在 zip()的帮助下执行跨列表的连接。

```py
# Python3 code to demonstrate working of
# Records List Concatenation
# using list comprehension + zip()

# initialize lists
test_list1 = [("g", "f"), ("g", "is"), ("be", "st")]
test_list2 = [("fg", "g"), ("gf", "best"), ("st", " gfg")]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# Records List Concatenation
# using list comprehension + zip()
res = [(x[0] + y[0], x[1] + y[1]) for x, y in zip(test_list1, test_list2)]

# printing result
print("The Concatenation across lists is : " + str(res))
```

**Output :**

```py
The original list 1 : [('g', 'f'), ('g', 'is'), ('be', 'st')]
The original list 2 : [('fg', 'g'), ('gf', 'best'), ('st', ' gfg')]
The Concatenation across lists is : [('gfg', 'fg'), ('ggf', 'isbest'), ('best', 'st gfg')]

```