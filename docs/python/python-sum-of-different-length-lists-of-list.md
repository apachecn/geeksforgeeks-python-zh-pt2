# Python–列表不同长度列表之和

> 原文:[https://www . geesforgeks . org/python-不同长度列表的总和/](https://www.geeksforgeeks.org/python-sum-of-different-length-lists-of-list/)

求列表的和是一个很常见的问题，已经被处理和讨论过很多次了，但是有时，我们要求更好地求列表的和和，也就是包括嵌套列表的和。让我们试着求出总数，然后解决这个特殊的问题。

**方法#1:使用列表理解+ `sum()`**
我们可以使用列表理解来解决这个问题，作为我们可能用来执行这个特定任务的常规循环的潜在速记。我们只需迭代并求和嵌套列表，最后使用 sum 函数返回累积和。

```py
# Python3 code to demonstrate
# Sum of Uneven Lists of list
# Using list comprehension + sum()

# initializing list
test_list = [[1, 4, 5], [7, 3], [4], [46, 7, 3]]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + sum()
# Sum of Uneven Lists of list
res = sum([ele for sub in test_list for ele in sub])

# print result
print("The total element sum in lists is : " + str(res))
```

**Output :**

```py
The original list : [[1, 4, 5], [7, 3], [4], [46, 7, 3]]
The total element sum in lists is : 80

```