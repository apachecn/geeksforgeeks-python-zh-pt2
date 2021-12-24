# Python |元组字符串的后置元素

> 原文:[https://www . geeksforgeeks . org/python-后元素-来自元组-字符串/](https://www.geeksforgeeks.org/python-rear-elements-from-tuple-strings/)

还有一个特殊的问题，可能并不常见，但可能会在 python 编程中使用元组时出现。由于元组是不可变的，它们很难操作，因此了解可能的变化解决方案总是有帮助的。本文解决了只提取元组中每个字符串的后索引元素的问题。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用列表理解**
几乎每一个问题都可以用列表理解作为简单方法的简写来解决，这个问题也不例外。在这种情况下，我们只需遍历每个列表，只挑选第 n-1 个索引元素来构建结果列表。

```
# Python3 code to demonstrate
# Rear elements from Tuple Strings
# using list comprehension

# initializing tuple
test_tuple = ('GfG', 'for', 'Geeks')

# printing original tuple 
print("The original tuple : " + str(test_tuple))

# using list comprehsion
# Rear elements from Tuple Strings
res = list(sub[len(sub) - 1] for sub in test_tuple)

# print result
print("The rear index string character list : " + str(res))
```

**Output :**

```
The original tuple : ('GfG', 'for', 'Geeks')
The rear index string character list : ['G', 'r', 's']

```