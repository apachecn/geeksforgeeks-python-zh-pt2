# Python |字符串列表中的子串移除

> 原文:[https://www . geesforgeks . org/python-substring-in-string-list 移除/](https://www.geeksforgeeks.org/python-substring-removal-in-string-list/)

在处理字符串时，最常用的应用程序之一是用另一个来移除字符串的一部分。因为字符串本身是不可变的，所以这个实用程序本身的知识非常有用。这里执行字符串列表中子字符串的删除。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+ `replace()`**
替换方法可以与列表理解技术相结合来实现这一特定任务。列表理解执行遍历列表的任务，替换方法用空字符串替换子字符串部分。

```
# Python3 code to demonstrate
# Substring removal in String list
# using list comprehension + replace()

# initializing list 
test_list = ['4', 'kg', 'butter', 'for', '40', 'bucks']

# printing original list 
print("The original list : " + str(test_list ))

# using list comprehension + replace()
# Substring removal in String list
res = [sub.replace('4', '') for sub in test_list]

# print result
print("The list after substring removal : " + str(res))
```

**Output :**

```
The original list : ['4', 'kg', 'butter', 'for', '40', 'bucks']
The list after substring removal : ['', 'kg', 'butter', 'for', '0', 'bucks']

```