# Python |匹配元素计数

> 原文:[https://www . geesforgeks . org/python-matching-elements-count/](https://www.geeksforgeeks.org/python-matching-elements-count/)

有时，在处理列表时，我们需要处理两个列表并搜索匹配项，然后只返回匹配项的索引数。当主列表的大小非常大时，查询整个列表的这个过程是不可行的，因此只有匹配索引有助于这个原因。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+ `index() + len()`**
这个问题可以通过使用 python 的索引函数来获得想要的索引来潜在地解决，并且列表理解可以用来将其扩展到整个字符串。len()用于返回匹配的总计数。

```py
# Python3 code to demonstrate
# Matching elements count
# using list comprehension and index() + len()

# initializing lists
test_list1 = [5, 4, 1, 3, 2]
test_list2 = [1, 2]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# using list comprehension and index() + len()
# Matching elements count
res = len([test_list1.index(i) for i in test_list2])

# print result
print("The Match indices list count is : " + str(res))
```

**Output :**

```py
The original list 1 : [5, 4, 1, 3, 2]
The original list 2 : [1, 2]
The Match indices list count is : 2

```