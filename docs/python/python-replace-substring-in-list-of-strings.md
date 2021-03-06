# Python |替换字符串列表中的子字符串

> 原文:[https://www . geesforgeks . org/python-替换-字符串列表中的子字符串/](https://www.geeksforgeeks.org/python-replace-substring-in-list-of-strings/)

使用字符串时，最常用的应用程序之一是用另一个字符串替换字符串的一部分。因为字符串本身是不可变的，所以这个实用程序本身的知识非常有用。这里执行字符串列表中子字符串的替换。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+ `replace()`**
替换方法可以与列表理解技术相结合来实现这一特定任务。列表理解执行遍历列表的任务，replace 方法用另一个替换子字符串的部分。

```py
# Python3 code to demonstrate
# Replace substring in list of strings
# using list comprehension + replace()

# initializing list 
test_list = ['4', 'kg', 'butter', 'for', '40', 'bucks']

# printing original list  
print("The original list : " + str(test_list ))

# using list comprehension + replace()
# Replace substring in list of strings
res = [sub.replace('4', '1') for sub in test_list]

# print result
print("The list after substring replacement : " + str(res))
```

**Output :**

```py
The original list : ['4', 'kg', 'butter', 'for', '40', 'bucks']
The list after substring replacement : ['1', 'kg', 'butter', 'for', '10', 'bucks']

```