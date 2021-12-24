# Python–将所有交叉列表元素对相乘

> 原文:[https://www . geesforgeks . org/python-multiple-all-cross-list-element-pairs/](https://www.geeksforgeeks.org/python-multiply-all-cross-list-element-pairs/)

有时，在使用 Python 列表时，我们会遇到一个问题，即我们需要将列表的每个元素与其他列表相乘。这在 web 开发和日常编程中都有应用。让我们讨论执行这项任务的某些方法。

**方法一:使用列表理解**
这是执行这个任务最直接的方法。在这种情况下，我们迭代列表，执行每个元素与其他元素的乘法，并将结果存储在新列表中。

```
# Python3 code to demonstrate 
# Multiply all cross list element pairs
# using list comprehension

# Initializing lists
test_list1 = [4, 5, 6]
test_list2 = [6, 4, 2]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Multiply all cross list element pairs
# using list comprehension
res = [i * j for j in test_list1 for i in test_list2]

# printing result 
print ("The multiplication list is : " + str(res))
```

**Output :**

```
The original list 1 is : [4, 5, 6]
The original list 2 is : [6, 4, 2]
The multiplication list is : [24, 16, 8, 30, 20, 10, 36, 24, 12]

```