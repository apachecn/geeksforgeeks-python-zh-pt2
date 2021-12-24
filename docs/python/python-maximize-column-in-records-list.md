# Python |记录列表中最大化列

> 原文:[https://www . geesforgeks . org/python-最大化-记录中的列-列表/](https://www.geeksforgeeks.org/python-maximize-column-in-records-list/)

有时，我们会遇到一个问题，我们处理一个复杂类型的矩阵列最大化，其中我们被赋予一个元组，我们需要执行其相似元素的最大化。这在机器学习领域有很好的应用。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`zip()` +列表理解**
这个问题可以使用列表理解来解决，该列表理解可以执行列最大化逻辑，并且 zip 函数用于绑定元素作为结果，并且也在垂直最大化时。

```py
# Python3 code to demonstrate
# Maximize Column in Records List
# using list comprehension + zip()

# initializing list 
test_list = [[(1, 4), (2, 3), (5, 2)], [(3, 7), (1, 9), (10, 5)]]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + zip()
# Maximize Column in Records List
res = [tuple(max(j) for j in zip(*i)) for i in zip(*test_list)]

# print result
print("The maximization of columns of tuple list : " + str(res))
```

**Output :**

```py
The original list : [[(1, 4), (2, 3), (5, 2)], [(3, 7), (1, 9), (10, 5)]]
The maximization of columns of tuple list : [(3, 7), (2, 9), (10, 5)]

```