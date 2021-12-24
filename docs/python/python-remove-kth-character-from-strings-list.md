# Python |从字符串列表中删除第 Kth 个字符

> 原文:[https://www . geesforgeks . org/python-remove-kth-字符串中的字符-列表/](https://www.geeksforgeeks.org/python-remove-kth-character-from-strings-list/)

有时，在处理数据时，我们可能会遇到一个问题，需要从字符串列表中删除一个特定的列，即第 Kth 个字符。字符串是不可变的，因此删除只是意味着重新创建一个没有 Kth 字符的字符串。让我们讨论执行这项任务的某些方法。

**方法一:使用列表理解+列表切片**
这是可以用来执行这个任务的简写。在本文中，我们只是使用切片重新创建所需的字符串，并使用列表理解将逻辑扩展到列表中的每个字符串元素。

```
# Python3 code to demonstrate working of
# Remove Kth character from strings list
# using list comprehension + list slicing

# initialize list 
test_list = ['akash', 'nikhil', 'manjeet', 'akshat']

# printing original list 
print("The original list : " + str(test_list))

# initialize K 
K = 3

# Remove Kth character from strings list
# using list comprehension + list slicing
res = [ele[:K] + ele[K + 1:] for ele in test_list]

# printing result
print("List after removal of Kth character of each string : " + str(res))
```

**Output :**

```
The original list : ['akash', 'nikhil', 'manjeet', 'akshat']
List after removal of Kth character of each string : ['akah', 'nikil', 'maneet', 'aksat']

```