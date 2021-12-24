# Python |交换元组列表中的元组元素

> 原文:[https://www . geesforgeks . org/python-swap-tuple-元素在元组列表中/](https://www.geeksforgeeks.org/python-swap-tuple-elements-in-list-of-tuples/)

在进行竞争性编程时，你可能会遇到一个问题，要求你使用 2D 平面和坐标进行工作。一个这样的子问题可以是交换 x，y 坐标元素。让我们讨论使用元组元素交换解决这个问题的某些方法。

**方法#1:使用列表理解**
这只是一个蛮力的方法来执行交换元素的较长的循环方法。在这种情况下，会创建一个新的元组列表，而不是就地交换。

```py
# Python3 code to demonstrate working of
# Swap tuple elements in list of tuples
# Using list comprehension

# initializing list
test_list = [(3, 4), (6, 5), (7, 8)]

# printing original list
print("The original list is : " + str(test_list))

# Swap tuple elements in list of tuples
# Using list comprehension
res = [(sub[1], sub[0]) for sub in test_list]

# printing result
print("The swapped tuple list is : " + str(res))
```

**Output :**

```py
The original list is : [(3, 4), (6, 5), (7, 8)]
The swapped tuple list is : [(4, 3), (5, 6), (8, 7)]

```