# Python–元组列表中相似的索引对

> 原文:[https://www . geesforgeks . org/python-相似索引-元组对列表/](https://www.geeksforgeeks.org/python-similar-index-pairs-in-tuple-lists/)

有时，在使用 Python 元组时，我们可能会遇到需要执行类似索引配对的问题。这种问题很特殊，但可能发生在某些领域。让我们讨论一下执行这项任务的具体方法。

> **输入** :
> test_list1 = [(5，，(1)、(8)、(10)，]
> test_list2 = [(8)、(1)、(1)、(11)、(9)，]
> T5】输出 : [[(5，8)]，[(1，1)]，[(8，11)]，[(10，9)]
> 
> **输入** :
> 测试 _ 列表 1 = [(5，6，7，6)]
> 测试 _ 列表 2 = [(8，6，7，9)]
> T5】输出:[(5，8)，(6，6)，(7，7)，(6，9)]

**方法:使用列表理解+ `zip()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 zip()执行压缩相似索引元素的任务，并使用列表理解来编译所有对。

```
# Python3 code to demonstrate working of 
# Similar index pairs in Tuple lists
# Using list comprehension + zip()

# initializing lists
test_list1 = [(5, 6), (1, 2), (8, 9), (10, 33)]
test_list2 = [(8, 7), (1, 3), (11, 23), (9, 4)]

# printing original list
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Similar index pairs in Tuple lists
# Using list comprehension + zip()
res = [list(zip(a, b)) for a, b in zip(test_list1, test_list2)]

# printing result 
print("The paired tuples : " + str(res)) 
```

**Output :**

```
The original list 1 is : [(5, 6), (1, 2), (8, 9), (10, 33)]
The original list 2 is : [(8, 7), (1, 3), (11, 23), (9, 4)]
The paired tuples : [[(5, 8), (6, 7)], [(1, 1), (2, 3)], [(8, 11), (9, 23)], [(10, 9), (33, 4)]]

```