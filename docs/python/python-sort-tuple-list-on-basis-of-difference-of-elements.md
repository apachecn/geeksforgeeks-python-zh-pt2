# Python |基于元素差异对元组列表进行排序

> 原文:[https://www . geesforgeks . org/python-sort-tuple-list-基于元素差异/](https://www.geeksforgeeks.org/python-sort-tuple-list-on-basis-of-difference-of-elements/)

有时，在处理数据时，我们可能会遇到排序问题。可以在多种类型的基础上执行排序。但本文讨论的是基于配对两个要素差异的排序。让我们讨论一下实现这一点的某些方法。

**方法一:使用`sorted()`+λ**
以上功能的组合可以用来解决这个问题。在这种情况下，排序由`sorted()`执行，并且λ函数作为键被馈送以执行期望的排序。

```py
# Python3 code to demonstrate working of
# Sort tuple list on basis of difference of elements
# using sorted() + lambda

# initialize list 
test_list = [(1, 4), (6, 5), (8, 10)]

# printing original list 
print("The original list : " + str(test_list))

# Sort tuple list on basis of difference of elements
# using sorted() + lambda
res = sorted(test_list, key = lambda sub: abs(sub[1] - sub[0]))

# printing result
print("List after sorting by difference : " + str(res))
```

**Output :**

```py
The original list : [(1, 4), (6, 5), (8, 10)]
List after sorting by difference : [(6, 5), (8, 10), (1, 4)]

```