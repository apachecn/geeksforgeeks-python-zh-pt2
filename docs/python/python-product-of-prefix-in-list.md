# Python |列表中前缀的乘积

> 原文:[https://www . geesforgeks . org/python-产品前缀列表/](https://www.geeksforgeeks.org/python-product-of-prefix-in-list/)

如今，特别是在竞争编程领域，计算前缀乘积的效用在许多问题中相当普遍和有特色。因此，有一个单一的解决方案会有很大的帮助。让我们讨论一下解决这个问题的某些方法。

**方法:使用列表理解+列表切片**
这个问题可以通过上述两个函数的组合来解决，其中我们使用列表理解将逻辑扩展到每个元素，然后计算产品，切片用于获取产品，直到特定的索引。

```py
# Python3 code to demonstrate
# Product of Prefix in list
# using list comprehension + list slicing 

# compute prod
def prod(test_list):
    res = 1
    for ele in test_list:
        res = res * ele
    return res

# initializing list
test_list = [3, 4, 1, 7, 9, 1]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + list slicing
# Product of Prefix in list
res = [prod(test_list[ : i + 1 ]) for i in range(len(test_list))]

# print result
print("The prefix prod list is : " + str(res))
```

**Output :**

```py
The original list : [3, 4, 1, 7, 9, 1]
The prefix prod list is : [3, 12, 12, 84, 756, 756]

```