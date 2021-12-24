# Python–移除列表中的负面元素

> 原文:[https://www . geesforgeks . org/python-remove-negative-elements-in-list/](https://www.geeksforgeeks.org/python-remove-negative-elements-in-list/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们需要从列表中移除所有负面元素。这种问题可以应用于许多领域，如学校编程和网络开发。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [6，4，3]
> **输出** : [6，4，3]
> 
> **输入** : test_list = [-6，-4]
> **输出** : []

**方法#1:使用列表理解**
以上功能的组合可以用来解决这个问题。在本文中，我们使用列表理解在一行中通过迭代来执行移除负元素的任务

```
# Python3 code to demonstrate working of 
# Remove Negative Elements in List
# Using list comprehension

# initializing list
test_list = [5, 6, -3, -8, 9, 11, -12, 2] 

# printing original list
print("The original list is : " + str(test_list))

# Remove Negative Elements in List
# Using list comprehension
res = [ele for ele in test_list if ele > 0]

# printing result 
print("List after filtering : " + str(res))
```

**Output :**

```
The original list is : [5, 6, -3, -8, 9, 11, -12, 2]
List after filtering : [5, 6, 9, 11, 2]

```

**方法 2:使用`filter()`+λ**
以上功能的组合也可以为这个问题提供一个替代方案。在本文中，我们扩展了使用 lambda 函数形成并使用 filter()扩展的保正逻辑。

```
# Python3 code to demonstrate working of 
# Remove Negative Elements in List
# Using filter() + lambda

# initializing list
test_list = [5, 6, -3, -8, 9, 11, -12, 2] 

# printing original list
print("The original list is : " + str(test_list))

# Remove Negative Elements in List
# Using filter() + lambda
res = list(filter(lambda x : x > 0, test_list))

# printing result 
print("List after filtering : " + str(res))
```

**Output :**

```
The original list is : [5, 6, -3, -8, 9, 11, -12, 2]
List after filtering : [5, 6, 9, 11, 2]

```