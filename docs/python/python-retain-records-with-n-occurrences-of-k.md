# Python–保留 K 出现 N 次的记录

> 原文:[https://www . geesforgeks . org/python-retain-records-with-n-occurs-k/](https://www.geeksforgeeks.org/python-retain-records-with-n-occurrences-of-k/)

有时，在使用 Python 元组列表时，我们可能会遇到一个问题，即我们需要保留 K 出现 N 次的所有记录。这种问题可能出现在诸如网络开发和日常编程等领域。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [(4，5，5，4)，(5，4，3)]，K = 5，N = 2
> **输出** : [(4，5，5，4)]
> **输入** : test_list = [(4，5，5，4)，(5，4，3)]，K = 5，N = 3
> **输出** : []

**方法#1:使用列表理解+计数()**
以上功能的组合可以用来解决这个问题。在本文中，我们使用列表理解来执行计数出现次数、条件和迭代次数的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Retain records with N occurrences of K
# Using count() + list comprehension

# initializing list
test_list = [(4, 5, 6, 4, 4), (4, 4, 3), (4, 4, 4), (3, 4, 9)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 4

# initializing N
N = 3

# Retain records with N occurrences of K
# Using count() + list comprehension
res = [ele for ele in test_list if ele.count(K) == N]

# printing result
print("Filtered tuples : " + str(res))
```

**Output : **

```
The original list is : [(4, 5, 6, 4, 4), (4, 4, 3), (4, 4, 4), (3, 4, 9)]
Filtered tuples : [(4, 5, 6, 4, 4), (4, 4, 4)]
```

**方法 2:使用列表理解+求和()**
以上函数的组合可以用来解决这个问题。在本文中，我们使用 sum()执行计算 K 的求和计数的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Retain records with N occurrences of K
# Using list comprehension + sum()

# initializing list
test_list = [(4, 5, 6, 4, 4), (4, 4, 3), (4, 4, 4), (3, 4, 9)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 4

# initializing N
N = 3

# Retain records with N occurrences of K
# Using list comprehension + sum()
res = [ele for ele in test_list if sum(cnt == K for cnt in ele) == N]

# printing result
print("Filtered tuples : " + str(res))
```

**Output : **

```
The original list is : [(4, 5, 6, 4, 4), (4, 4, 3), (4, 4, 4), (3, 4, 9)]
Filtered tuples : [(4, 5, 6, 4, 4), (4, 4, 4)]
```