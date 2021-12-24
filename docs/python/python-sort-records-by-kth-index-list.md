# Python–按第 k 个索引列表对记录进行排序

> 原文:[https://www . geesforgeks . org/python-sort-records-by-kth-index-list/](https://www.geeksforgeeks.org/python-sort-records-by-kth-index-list/)

有时，在使用 Python Records 时，我们可能会遇到一个问题，我们需要通过 Tuple 中的某个元素对记录进行排序，这也可能是有时，一个列表和排序必须通过该列表的 Kth 索引来执行。这是一个不常见的问题，但在 web 开发等领域可能会有用例。让我们讨论一下执行这项任务的具体方法。

> **输入** :
> test_list = [([4，5]，' Gfg ')，([8，4]，' is ')，([2，3]，' best')]
> K = 0
> **输出** : [([2，3]，' best ')，([4，5]，' Gfg ')，([8，4]，' is')]
> **输入** :
> test_list = [([4，7]

**方法:使用 sort() + lambda**
以上函数的组合可以用来解决这个问题。在这种情况下，我们使用 sort 执行排序任务，必须执行排序的参数和索引是使用 lambda 函数提供的。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Sort Records by Kth Index List
# Using sort() + lambda

# initializing list
test_list = [([4, 5, 7, 3], 'Gfg'), ([8, 6, 3, 1], 'is'),
                                 ([2, 3, 5, 2], 'best')]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 1

# Sort Records by Kth Index List
# Using sort() + lambda
test_list.sort(key = lambda sub: sub[0][K])

# printing result
print("The records after sorting : " + str(test_list))
```

**Output : **

原列表为:[([4，5，7，3]，' Gfg ')，([8，6，3，1]，' is ')，([2，3，5，2]，' best')]
排序后的记录:[([2，3，5，2]，' best ')，([4，5，7，3]，' Gfg ')，([8，6，3，1]，' is')]