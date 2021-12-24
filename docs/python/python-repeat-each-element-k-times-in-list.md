# Python |在列表中重复每个元素 K 次

> 原文:[https://www . geesforgeks . org/python-repeat-每个元素-k-times-in-list/](https://www.geeksforgeeks.org/python-repeat-each-element-k-times-in-list/)

很多时候我们有这个特殊的用例，其中我们需要重复列表的每个元素 K 次。制作双重克隆的问题已经讨论过了，但是这个问题扩展到允许一个灵活的变量定义元素重复的次数。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解**
这个特殊的任务通常需要 2 个循环，列表理解可以在一行中执行这个特殊的任务，从而减少代码的行数，提高代码的可读性。

```
# Python3 code to demonstrate 
# repeat element K times
# using list comprehension

# initializing list of lists
test_list = [4, 5, 6]

# printing original list 
print("The original list : " +  str(test_list))

# declaring magnitude of repetition
K = 3

# using list comprehension
# repeat elements K times
res =  [ele for ele in test_list for i in range(K)]

# printing result 
print("The list after adding elements :  " + str(res))
```

**Output :**

```
The original list : [4, 5, 6]
The list after adding elements :  [4, 4, 4, 5, 5, 5, 6, 6, 6]

```