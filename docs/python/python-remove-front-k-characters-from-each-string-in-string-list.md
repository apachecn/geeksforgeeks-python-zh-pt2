# Python–删除字符串列表

中每个字符串的前 K 个字符

> 原文:[https://www . geesforgeks . org/python-remove-front-k-characters-from-in-string-list/](https://www.geeksforgeeks.org/python-remove-front-k-characters-from-each-string-in-string-list/)

有时，我们会遇到这样一个问题，我们需要从每个字符串中删除前 K 个字符，这可能是我们误加的，我们需要将其扩展到整个列表。这种类型的实用程序在 web 开发中很常见。有人手来做这项特殊的工作总是一个优势。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+列表切片**
这个任务可以通过使用列表切片移除字符的能力来执行，并且列表理解有助于将该逻辑扩展到整个列表。

```
# Python3 code to demonstrate
# Remove front K elements in String List
# using list comprehension + list slicing

# initializing list
test_list = ['Manjeet', 'Akash', 'Akshat', 'Nikhil']

# printing original list 
print("The original list : " + str(test_list))

# initializing K 
K = 3

# using list comprehension + list slicing
# Remove front K elements in String List
res = [sub[K :] for sub in test_list]

# printing result
print("The list after removing initial K characters : " + str(res))
```

**Output :**

```
The original list : ['Manjeet', 'Akash', 'Akshat', 'Nikhil']
The list after removing initial K characters : ['jeet', 'sh', 'hat', 'hil']

```