# Python |删除字符串列表中的最后一个字符

> 原文:[https://www . geesforgeks . org/python-移除字符串列表中的最后一个字符/](https://www.geeksforgeeks.org/python-remove-last-character-in-list-of-strings/)

有时，我们会遇到一个问题，我们需要删除每个字符串中的最后一个字符，这可能是我们误加的，我们需要将其扩展到整个列表。这种类型的实用程序在 web 开发中很常见。有人手来做这项特殊的工作总是一个优势。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+列表切片**
这个任务可以通过使用列表切片移除字符的能力来执行，并且列表理解有助于将该逻辑扩展到整个列表。

```py
# Python3 code to demonstrate
# remove last character from list of strings
# using list comprehension + list slicing

# initializing list
test_list = ['Manjeets', 'Akashs', 'Akshats', 'Nikhils']

# printing original list 
print("The original list : " + str(test_list))

# using list comprehension + list slicing
# remove last character from list of strings
res = [sub[ : -1] for sub in test_list]

# printing result
print("The list after removing last characters : " + str(res))
```

**Output :**

```py
The original list : ['Manjeets', 'Akashs', 'Akshats', 'Nikhils']
The list after removing last characters : ['Manjeet', 'Akash', 'Akshat', 'Nikhil']

```