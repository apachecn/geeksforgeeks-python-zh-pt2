# Python–保留所有 K 元素行

> 原文:[https://www . geesforgeks . org/python-retain-all-k-elements-row/](https://www.geeksforgeeks.org/python-retain-all-k-elements-rows/)

有时，在使用 Python 列表时，我们会遇到一个问题，即我们需要保留只有 K 个元素的行。这种应用可以出现在以矩阵为输入的数据域中。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [[7，6]，[4，4]，[1，2]，[4]]，K = 4
> **输出** : [[4，4]，[4]]
> 
> **输入** : test_list = [[7，6]，[7，4]，[1，2]，[9]]，K = 4
> **输出** : []

**方法#1:使用列表理解+ `any()`**
上述功能的组合提供了一种执行该任务的方式。在本例中，我们使用 any()执行过滤掉除 K 之外的任何元素的行的任务。

```
# Python3 code to demonstrate working of 
# Retain all K elements Rows
# Using list comprehension + any()

# initializing list
test_list = [[2, 4, 6], [2, 2, 2], [2, 3], [2, 2]]

# printing original list 
print("The original list : " + str(test_list))

# initializing K 
K = 2

# Retain all K elements Rows
# Using list comprehension + any()
res = [ele for ele in test_list if not any(el != K for el in ele)]

# printing result 
print("Matrix after filtering : " + str(res))
```

**Output :**

```
The original list : [[2, 4, 6], [2, 2, 2], [2, 3], [2, 2]]
Matrix after filtering : [[2, 2, 2], [2, 2]]

```

**方法 2:使用列表理解+ `all()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 all()检查行的所有元素是否都等于 K。

```
# Python3 code to demonstrate working of 
# Retain all K elements Rows
# Using list comprehension + all()

# initializing list
test_list = [[2, 4, 6], [2, 2, 2], [2, 3], [2, 2]]

# printing original list 
print("The original list : " + str(test_list))

# initializing K 
K = 2

# Retain all K elements Rows
# Using list comprehension + all()
res = [ele for ele in test_list if all(el == K for el in ele)]

# printing result 
print("Matrix after filtering : " + str(res))
```

**Output :**

```
The original list : [[2, 4, 6], [2, 2, 2], [2, 3], [2, 2]]
Matrix after filtering : [[2, 2, 2], [2, 2]]

```