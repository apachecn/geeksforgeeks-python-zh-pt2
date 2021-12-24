# Python |系列 K 整除元素

> 原文:[https://www . geesforgeks . org/python-series-k-可分元素/](https://www.geeksforgeeks.org/python-series-k-divisible-elements/)

本文关注的问题非常具体，在不同领域可能用处不大。但这种解决方式可能会为解决潜在的类似问题打开大门，因此值得一读。本文解决了测试一个列表是否包含 K 整除数列的问题。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`sum() + list comprehension + zip() + any()`**
结合以上功能可以解决这个问题。这种方法分两步解决问题。在第一步中，我们使用列表理解和 zip 函数计算所有可能的 N 对，在第二步中，我们使用 sum 和任何函数来测试 N 个可分的结果，如果我们找到其中的任何一个，我们返回正。

```py
# Python3 code to demonstrate
# Series K divisible elements
# using sum() + zip() + any() + list comprehension

# initializing list
test_list = [1, 5, 6, 4, 8, 12]

# printing original list
print("The original list : " + str(test_list))

# initializing N 
N = 3

# initializing K 
K = 4

# using sum() + zip() + any() + list comprehension
# Series K divisible elements
temp = ( test_list[i : i + N] for i in range(len(test_list) - N + 1) )
res = any( sum(ele % K for ele in temps) % N == 0 for temps in temp )

# print result
print("Does list contain the desired consecution : " + str(res))
```

**Output :**

```py
The original list : [1, 5, 6, 4, 8, 12]
Does list contain the desired consecution : True

```