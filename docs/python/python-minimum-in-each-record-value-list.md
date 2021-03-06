# Python–每个记录值列表中的最小值

> 原文:[https://www . geesforgeks . org/python-每条记录中的最小值-值列表/](https://www.geeksforgeeks.org/python-minimum-in-each-record-value-list/)

很多时候，在处理任何语言的容器时，我们都会遇到不同形式的元组列表，元组本身有时可以有比本机数据类型更多的数据类型，并且可以有列表作为它们的属性。本文讨论列表作为元组属性的最小值。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `min()`**
这个特殊的问题可以通过使用列表理解结合 min 函数来解决，其中我们使用 min 函数来找到列表的 min 作为元组属性，并使用列表理解来迭代列表。

```py
# Python3 code to demonstrate 
# Record Value list Minimum
# using list comprehension + min() 

# initializing list 
test_list = [('key1', [3, 4, 5]), ('key2', [1, 4, 2]), ('key3', [9, 3])] 

# printing original list 
print("The original list : " + str(test_list)) 

# using list comprehension + min() 
# Record Value list Minimum
res = [(key, min(lst)) for key, lst in test_list] 

# print result 
print("The list tuple attribute minimum is : " + str(res)) 
```

**Output :**

```py
The original list : [('key1', [3, 4, 5]), ('key2', [1, 4, 2]), ('key3', [9, 3])]
The list tuple attribute minimum is : [('key1', 3), ('key2', 1), ('key3', 3)]

```