# Python |反转字符串列表中的所有字符串

> 原文:[https://www . geesforgeks . org/python-reverse-全字符串列表/](https://www.geeksforgeeks.org/python-reverse-all-strings-in-string-list/)

给定一个列表，我们总是会遇到这样的情况:我们需要对列表中的每个元素应用特定的函数。这可以通过应用循环并对每个元素执行操作来轻松完成。但是用人手不足来解决这个问题总是有好处的，并且有助于更好地关注问题的重要方面。让我们讨论对字符串列表中的每个字符串执行反向操作的某些方法。

**方法#1:使用列表理解**
该方法在后台执行与循环构造相同的任务。这种特殊方法提供的优势是这是一个单一的线性，也提高了代码的可读性。

```py
# Python3 code to demonstrate 
# Reverse All Strings in String List
# using list comprehension

# initializing list 
test_list = ["geeks", "for", "geeks", "is", "best"]

# printing original list
print ("The original list is : " + str(test_list))

# using list comprehension
# Reverse All Strings in String List
res = [i[::-1] for i in test_list]

# printing result
print ("The reversed string list is : " + str(res))
```

**Output :**

```py
The original list is : ['geeks', 'for', 'geeks', 'is', 'best']
The reversed string list is : ['skeeg', 'rof', 'skeeg', 'si', 'tseb']

```