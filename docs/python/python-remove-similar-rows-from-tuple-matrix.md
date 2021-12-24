# Python–从元组矩阵中移除相似行

> 原文:[https://www . geesforgeks . org/python-从元组矩阵中移除相似行/](https://www.geeksforgeeks.org/python-remove-similar-rows-from-tuple-matrix/)

有时，在使用元组矩阵时，我们会遇到一个问题，我们会得到许多相似的数据，即行中的元素是相同的，只是元组的顺序不同，有时希望删除它们。这种问题可以应用于诸如 web 开发和日常编程等领域。让我们讨论执行这项任务的某些方法。

> **输入**:test _ list =[(4，5)，(3，2)]，[(3，2)，(4，5)]，[(3，2)，(4，5)]
> **输出** : {((4，5)，(3，2))
> 
> **输入**:test _ list =[(4，6)，(3，2)]，[(3，2)，(4，5)]，[(3，2)，(4，5)]
> **输出** : {((3，2)，(4，6))，((4，5)，(3，2))

**方法一:使用`set() + tuple() + sorted()` +列表理解**
以上功能的组合可以解决这个问题。在这种情况下，我们首先执行排序，然后将行转换为集合，这将自动删除重复的行。

```py
# Python3 code to demonstrate working of 
# Remove Similar Rows from Tuple Matrix
# Using set() + tuple() + sorted() + list comprehension

# initializing lists
test_list = [[(4, 5), (3, 2)], [(2, 2), (4, 6)], [(3, 2), (4, 5)]]

# printing original list
print("The original list is : " + str(test_list))

# Remove Similar Rows from Tuple Matrix
# Using set() + tuple() + sorted() + list comprehension
res = set([tuple(set(sub)) for sub in test_list])

# printing result 
print("Tuple matrix after removal : " + str(res))
```

**Output :**

```py
The original list is : [[(4, 5), (3, 2)], [(2, 2), (4, 6)], [(3, 2), (4, 5)]]
Tuple matrix after removal : {((4, 6), (2, 2)), ((4, 5), (3, 2))}

```

**方法 2:使用`set() + frozenset()` +生成器表达式**
以上功能的组合可以解决这个问题。在本文中，我们使用 frozenset()执行排序和元组转换的任务。

```py
# Python3 code to demonstrate working of 
# Remove Similar Rows from Tuple Matrix
# Using set() + frozenset() + generator expression

# initializing lists
test_list = [[(4, 5), (3, 2)], [(2, 2), (4, 6)], [(3, 2), (4, 5)]]

# printing original list
print("The original list is : " + str(test_list))

# Remove Similar Rows from Tuple Matrix
# Using set() + frozenset() + generator expression
res = set([frozenset(sub) for sub in test_list])

# printing result 
print("Tuple matrix after removal : " + str(res))
```

**Output :**

```py
The original list is : [[(4, 5), (3, 2)], [(2, 2), (4, 6)], [(3, 2), (4, 5)]]
Tuple matrix after removal : {frozenset({(4, 5), (3, 2)}), frozenset({(4, 6), (2, 2)})}

```