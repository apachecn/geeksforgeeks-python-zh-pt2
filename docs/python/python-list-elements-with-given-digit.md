# Python–列出给定数字的元素

> 原文:[https://www . geesforgeks . org/python-list-elements-with-given-digit/](https://www.geeksforgeeks.org/python-list-elements-with-given-digit/)

给定元素列表和一个数字 K，提取所有包含 K 数字的数字。

> **输入**:test _ list =【56，72，875，9，173】，K = 5
> **输出**:【56，875】
> **解释** : 56 和 875 有“5”作为数字，因此被提取。
> 
> **输入** : test_list = [56，72，875，9，173]，K = 4
> **输出** : []
> **解释**:没有数字有 4 作为数字。

**方法#1:使用列表理解+ str()**

这是执行这项任务的方法之一。在这种情况下，我们将数字和元素转换为字符串，然后检查它是否在该元素内。在列表理解中进行元素迭代，得到单行解。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Elements with K digit
# Using list comprehension + str()

# initializing list
test_list = [56, 72, 875, 9, 173]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 7

# extracting all elements with digit K using
# in operator after string conversion using str()
res = [ele for ele in test_list if str(K) in str(ele)]

# printing result
print("Elements with digit K : " + str(res))
```

**Output**

```
The original list is : [56, 72, 875, 9, 173]
Elements with digit K : [72, 875, 173]
```

**方法 2:使用 filter() + lambda + str()**

这是解决这个问题的另一种方法。在本文中，我们使用 filter() + lambda 和 str()来检查条件并提取所需的元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Elements with K digit
# Using filter() + lambda + str()

# initializing list
test_list = [56, 72, 875, 9, 173]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 7

# using filter() and lambda to perform conditionals
# using str() to perform data type conversions
res = list(filter(lambda ele: str(K) in str(ele), test_list))

# printing result
print("Elements with digit K : " + str(res))
```

**Output**

```
The original list is : [56, 72, 875, 9, 173]
Elements with digit K : [72, 875, 173]
```