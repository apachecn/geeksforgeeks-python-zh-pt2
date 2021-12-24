# Python–从列表中移除空列表

> 原文:[https://www . geesforgeks . org/python-remove-empty-list-from-list/](https://www.geeksforgeeks.org/python-remove-empty-list-from-list/)

有时，在处理 python 数据时，我们会遇到一个问题，需要过滤掉某些空数据。这些可以是无、空字符串等。这在许多领域都有应用。让我们讨论可以执行空列表移除的某些方法。

**方法一:利用列表理解**
这是解决这个问题的方法之一。在这种情况下，我们遍历列表，不包括空的列表。

```py
# Python3 code to demonstrate 
# Remove empty List from List
# using list comprehension

# Initializing list 
test_list = [5, 6, [], 3, [], [], 9]

# printing original list 
print("The original list is : " + str(test_list))

# Remove empty List from List
# using list comprehension
res = [ele for ele in test_list if ele != []]

# printing result 
print ("List after empty list removal : " + str(res))
```

**Output :**

```py
The original list is : [5, 6, [], 3, [], [], 9]
List after empty list removal : [5, 6, 3, 9]

```