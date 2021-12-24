# Python–从字符串列表中删除前导 0

> 原文:[https://www . geesforgeks . org/python-remove-leader-0-from-strings-list/](https://www.geeksforgeeks.org/python-remove-leading-0-from-strings-list/)

有时，在使用 Python 时，我们可能会遇到一个问题，即我们有数据，需要在其中执行处理，然后将数据向前传递。一种处理方法是移除在数据传输时可能附加到字符串的杂散 0。让我们讨论执行这项任务的某些方法。

**方法一:使用`lstrip()` +列表理解**
这是可以帮助完成该任务的一个班轮之一。在本文中，我们使用 lstrip 剥离前导 0，并使用列表理解将逻辑扩展到列表。

```py
# Python3 code to demonstrate 
# Remove leading 0 from Strings List
# using lstrip() + list comprehension

# Initializing list
test_list = ['012', '03', '044', '09']

# printing original list
print("The original list is : " + str(test_list))

# Remove leading 0 from Strings List
# using lstrip() + list comprehension
res = [ele.lstrip('0') for ele in test_list]

# printing result 
print ("The string list after leading 0 removal : " + str(res))
```

**Output :**

```py
The original list is : ['012', '03', '044', '09']
The string list after leading 0 removal : ['12', '3', '44', '9']

```