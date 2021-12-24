# Python–重复列表中的替代元素

> 原文:[https://www . geesforgeks . org/python-repeat-alternate-elements-in-list/](https://www.geeksforgeeks.org/python-repeat-alternate-elements-in-list/)

很多时候，我们有这个特殊的用例，其中我们需要重复 K 次列表的替换元素。制作双重克隆的问题已经讨论过了，但是这个问题扩展到允许一个灵活的变量定义元素重复的次数。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解**
这个特殊的任务通常需要 2 个循环，列表理解可以在一行中执行这个特殊的任务，从而减少代码的行数，提高代码的可读性。

```py
# Python3 code to demonstrate 
# Alternate Element Repetition
# using list comprehension

# initializing list of lists
test_list = [4, 5, 6]

# printing original list 
print("The original list : " + str(test_list))

# declaring magnitude of repetition
K = 3

# using list comprehension
# Alternate Element Repetition
res = [ele for idx, ele in enumerate(test_list) for i in range(K) if idx % 2 == 0]

# printing result 
print("The list after alternate repeating elements : " + str(res))
```

**Output :**

```py
The original list : [4, 5, 6]
The list after alternate repeating elements : [4, 4, 4, 6, 6, 6]

```