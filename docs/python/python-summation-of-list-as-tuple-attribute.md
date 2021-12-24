# Python |列表作为元组属性的求和

> 原文:[https://www . geeksforgeeks . org/python-列表总和作为元组属性/](https://www.geeksforgeeks.org/python-summation-of-list-as-tuple-attribute/)

很多时候，在处理任何语言的容器时，我们都会遇到不同形式的元组列表，元组本身有时可以有比本机数据类型更多的数据类型，并且可以有列表作为它们的属性。本文讨论列表作为元组属性的求和。让我们讨论执行这项任务的某些方法。

**方法一:使用列表理解+ `sum()`**

这个特殊的问题可以通过使用列表理解结合求和函数来解决，其中我们使用求和函数来找到列表作为元组属性的和，并且使用列表理解来迭代列表。

```
# Python3 code to demonstrate
# Summation of list as tuple attribute
# using list comprehension + sum()

# initializing list
test_list = [('key1', [3, 4, 5]), ('key2', [1, 4, 2]), ('key3', [9, 3])]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + sum()
# Summation of list as tuple attribute
res = [(key, sum(lst)) for key, lst in test_list]

# print result
print("The list tuple attribute summation is : " + str(res))
```

**Output :**

> 原始列表:[('key1 '，[3，4，5])，(' key2 '，[1，4，2])，(' key3 '，[9，3])]
> 列表元组属性求和为:[('key1 '，12)、(' key2 '，7)、(' key3 '，12)]

**方法 2:使用 map + lambda + `sum()`**
上述问题也可以通过使用 map 函数将逻辑扩展到整个列表来解决，sum 函数可以执行与上述方法类似的任务。

```
# Python3 code to demonstrate
# Summation of list as tuple attribute
# using map() + lambda + sum()

# initializing list
test_list = [('key1', [3, 4, 5]), ('key2', [1, 4, 2]), ('key3', [9, 3])]

# printing original list
print("The original list : " + str(test_list))

# using map() + lambda + sum()
# Summation of list as tuple attribute
res = list(map(lambda x: (x[0], sum(x[1])), test_list))

# print result
print("The list tuple attribute summation is : " + str(res))
```

**Output :**

> 原始列表:[('key1 '，[3，4，5])，(' key2 '，[1，4，2])，(' key3 '，[9，3])]
> 列表元组属性求和为:[('key1 '，12)、(' key2 '，7)、(' key3 '，12)]