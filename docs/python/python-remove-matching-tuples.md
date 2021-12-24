# Python |移除匹配元组

> 原文:[https://www . geesforgeks . org/python-remove-matching-元组/](https://www.geeksforgeeks.org/python-remove-matching-tuples/)

从两个列表中移除匹配元素并构建一个新列表的问题已经在前面讨论过了，这个新列表只包含第二个列表中不存在的过滤元素，但是有时，我们不止有一个基本元素，还有一个元组作为列表的元素。处理这样的案件需要不同类型的处理。让我们讨论如何解决这个问题。

**方法#1:使用列表理解**
这个特殊的任务可以通过使用列表理解作为 for 循环的简写来完成，我们会用到这个循环。我们只是检查另一个元组中是否存在一个元组，并据此做出决定。

```py
# Python3 code to demonstrate
# filter repeated tuple
# using list comprehension

# initializing lists 
test_list1 = [('Geeks', 'for'), ('Geeks', 'is'), ('Computer', 'Science')]
test_list2 = [('Geeks', 'for'), ('Geeks', 'is')]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 1 : " + str(test_list2))

# using list comprehension
# filter repeated tuple
res =  [sub for sub in test_list1 if sub not in test_list2]

# print result
print("The filtered list of tuples : " + str(res))
```

**Output :**

```py
The original list 1 : [('Geeks', 'for'), ('Geeks', 'is'), ('Computer', 'Science')]
The original list 1 : [('Geeks', 'for'), ('Geeks', 'is')]
The filtered list of tuples : [('Computer', 'Science')]

```