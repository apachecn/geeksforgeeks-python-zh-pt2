# Python–测试公共值是否大于 K

> 原文:[https://www . geesforgeks . org/python-test-if-common-values-大于-k/](https://www.geeksforgeeks.org/python-test-if-common-values-are-greater-than-k/)

有时，在使用列表时，我们会遇到一个问题，需要跟踪列表中的公共元素。这是很常见的，我们经常有结构来解决这个问题。但是有时，如果两个列表包含一个快速的 K 个匹配元素，我们需要将它们视为匹配。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`set() + len()`**
以上方法的组合可以用来解决这个任务。在本文中，我们首先将每个列表转换为集合，然后使用 len()检查匹配元素是否大于 k。

```py
# Python3 code to demonstrate 
# Test if common values are greater than K
# using len() + set()

# Initializing lists
test_list1 = ['Gfg', 'is', 'for', 'Geeks']
test_list2 = [1, 'Gfg', 2, 'Geeks']

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Initializing K 
K = 2

# Test if common values are greater than K
# using len() + set()
res = len(set(test_list1) & set(test_list2)) >= K

# printing result 
print ("Are common elements greater than K ? : " + str(res))
```

**Output :**

```py
The original list 1 is : ['Gfg', 'is', 'for', 'Geeks']
The original list 2 is : [1, 'Gfg', 2, 'Geeks']
Are common elements greater than K ? : True

```