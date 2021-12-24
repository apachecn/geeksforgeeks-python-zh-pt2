# Python |将嵌套列表配对组合成元组列表

> 原文:[https://www . geesforgeks . org/python-对组合嵌套列表到元组列表/](https://www.geeksforgeeks.org/python-pair-and-combine-nested-list-to-tuple-list/)

有时，我们需要在数据类型之间进行转换，主要是因为将它们馈送给某些函数或输出的原因。本文解决了一个非常特殊的问题，即列表中的索引配对，然后构建这些配对的元组列表。让我们讨论一下如何实现这个问题的解决。

**方法#1:使用`zip()` +列表理解**
我们可以使用`zip` 函数链接到每个元素的相似索引，列表理解可以用于执行转换为元组背后的逻辑，并将逻辑扩展到所有子列表。

```py
# Python3 code to demonstrate
# Pairing and combining nested list to tuple list
# using zip() + list comprehension

# initializing lists 
test_list1 = [[1, 4, 5], [8, 7], [2]]
test_list2 = [['g', 'f', 'g'], ['f', 'r'], ['u']]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# using zip() + list comprehension
# Pairing and combining nested list to tuple list
res = [(u, v) for x, y in zip(test_list1, test_list2)
                               for u, v in zip(x, y)]

# print result
print("The paired list of tuple is : " + str(res))
```

**Output :**

> 原列表 1 : [[1，4，5]，[8，7]，[2]]
> 原列表 2:[[[' g '，' f '，' g']，['f '，' r']，[' u ']
> 元组的配对列表为:[(1，' g ')，(4，' f ')，(5，' g '，(8，' f ')，(7，' r '，(2，' u')]