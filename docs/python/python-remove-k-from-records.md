# Python–从记录中移除 K

> 原文:[https://www.geeksforgeeks.org/python-remove-k-from-records/](https://www.geeksforgeeks.org/python-remove-k-from-records/)

有时，在使用 Python 元组时，我们可能会遇到一个问题，即我们需要从列表中移除所有 K。这项任务可以应用于许多领域，如网页开发和日常编程。让我们讨论执行这项任务的某些方法。

> **输入** :
> 测试 _ 列表= [(5，6，7)，(2，5，7)]
> K = 7
> **输出** : [(5，6)，(2，5)]
> 
> **输入** :
> 测试 _ 列表= [(5，6，7)，(2，5，7)]
> K = 5
> **输出** : [(6，7)，(2，7)]

**方法一:使用列表理解**
这是可以执行这个任务的方式之一。在本文中，我们使用列表理解来执行获取条件检查和重新创建新列表的任务。

```
# Python3 code to demonstrate working of 
# Remove K from Records
# Using list comprehension

# initializing list
test_list = [(5, 6, 7), (2, 5), (1, ), (7, 8), (9, 7, 2, 1)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 7

# Remove K from Records
# Using list comprehension
res = [tuple(ele for ele in sub if ele != K) for sub in test_list]

# printing result 
print("The records after removing K : " + str(res)) 
```

**Output :**

```
The original list is : [(5, 6, 7), (2, 5), (1, ), (7, 8), (9, 7, 2, 1)]
The records after removing K : [(5, 6), (2, 5), (1, ), (8, ), (9, 2, 1)]

```

**方法 2:使用`filter()`+λ**
以上功能的组合可以解决这个问题。在本例中，我们使用 filter()和 lambda 功能执行移除所有 Ks 的任务。

```
# Python3 code to demonstrate working of 
# Remove K from Records
# Using filter() + lambda

# initializing list
test_list = [(5, 6, 7), (2, 5), (1, ), (7, 8), (9, 7, 2, 1)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 7

# Remove K from Records
# Using filter() + lambda
res = [tuple(filter(lambda ele: ele != 0, sub)) for sub in test_list]

# printing result 
print("The records after removing K : " + str(res)) 
```

**Output :**

```
The original list is : [(5, 6, 7), (2, 5), (1, ), (7, 8), (9, 7, 2, 1)]
The records after removing K : [(5, 6), (2, 5), (1, ), (8, ), (9, 2, 1)]

```