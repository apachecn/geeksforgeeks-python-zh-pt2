# Python |按元组的第 n 个元素对元组列表进行排序

> 原文:[https://www . geesforgeks . org/python-sort-tuple-list-by-n-element-of-tuple/](https://www.geeksforgeeks.org/python-sort-tuple-list-by-nth-element-of-tuple/)

有时候，在使用 Python 列表时，我们会遇到一个问题，我们需要根据任何元组元素对列表进行排序。这些必须是执行特定元组索引排序的通用方法。这在 web 开发领域有很好的实用性。让我们讨论执行这项任务的某些方法。

**方法一:使用`sort() + lambda`**
以上功能的组合可以用来执行此任务。在这种情况下，我们只需向`sort()`传递一个 lambda 函数，该函数带有适当的元组元素索引，根据该索引必须执行排序。

```
# Python3 code to demonstrate working of
# Sort tuple list by Nth element of tuple
# using sort() + lambda

# initializing list
test_list = [(4, 5, 1), (6, 1, 5), (7, 4, 2), (6, 2, 4)]

# printing original list
print("The original list is : " + str(test_list))

# index according to which sort to perform
N = 1

# Sort tuple list by Nth element of tuple
# using sort() + lambda
test_list.sort(key = lambda x: x[N])

# printing result 
print("List after sorting tuple by Nth index sort : " + str(test_list))
```

**Output :**

```
The original list is : [(4, 5, 1), (6, 1, 5), (7, 4, 2), (6, 2, 4)]
List after sorting tuple by Nth index sort : [(6, 1, 5), (6, 2, 4), (7, 4, 2), (4, 5, 1)]

```