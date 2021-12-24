# Python–删除连续 K 个元素记录

> 原文:[https://www . geesforgeks . org/python-remove-continuous-k-element-records/](https://www.geeksforgeeks.org/python-remove-consecutive-k-element-records/)

有时，在使用 Python 记录时，我们可能会遇到一个问题，即我们需要根据元组中连续 K 个元素的存在来移除记录。这种问题很特殊，但可以应用于数据领域。让我们讨论执行这项任务的某些方法。

> **输入** :
> 测试 _ 列表= [(4，5)，(5，6)，(1，3)，(0，0)]
> K = 0
> T5】输出 : [(4，5)，(5，6)，(1，3)]
> 
> **输入** :
> 测试 _ 列表= [(4，5)，(5，6)，(1，3)，(5，4)]
> K = 5
> T5】输出 : [(4，5)，(5，6)，(1，3)，(5，4)]

**方法一:使用`zip()` +列表理解**
以上功能的组合可以解决这个问题。在这种情况下，我们需要使用 zip()组合两个连续的片段，并在列表理解中执行比较。

```
# Python3 code to demonstrate working of 
# Remove Consecutive K element records
# Using zip() + list comprehension

# initializing list
test_list = [(4, 5, 6, 3), (5, 6, 6, 9), (1, 3, 5, 6), (6, 6, 7, 8)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 6

# Remove Consecutive K element records
# Using zip() + list comprehension
res = [idx for idx in test_list if (K, K) not in zip(idx, idx[1:])]

# printing result 
print("The records after removal : " + str(res)) 
```

**Output :**

```
The original list is : [(4, 5, 6, 3), (5, 6, 6, 9), (1, 3, 5, 6), (6, 6, 7, 8)]
The records after removal : [(4, 5, 6, 3), (1, 3, 5, 6)]

```

**方法二:使用`any()` +列表理解**
以上功能的组合可以解决这个问题。在这种情况下，我们使用 any()检查连续的元素，并使用列表理解来重新制作列表。

```
# Python3 code to demonstrate working of 
# Remove Consecutive K element records
# Using any() + list comprehension

# initializing list
test_list = [(4, 5, 6, 3), (5, 6, 6, 9), (1, 3, 5, 6), (6, 6, 7, 8)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 6

# Remove Consecutive K element records
# Using any() + list comprehension
res = [idx for idx in test_list if not any(idx[j] == K and idx[j + 1] == K for j in range(len(idx) - 1))]

# printing result 
print("The records after removal : " + str(res)) 
```

**Output :**

```
The original list is : [(4, 5, 6, 3), (5, 6, 6, 9), (1, 3, 5, 6), (6, 6, 7, 8)]
The records after removal : [(4, 5, 6, 3), (1, 3, 5, 6)]

```