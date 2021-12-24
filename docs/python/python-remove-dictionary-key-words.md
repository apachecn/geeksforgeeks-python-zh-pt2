# Python–删除词典关键词

> 原文:[https://www . geesforgeks . org/python-remove-dictionary-key-words/](https://www.geeksforgeeks.org/python-remove-dictionary-key-words/)

有时，在使用 Python 字符串时，我们可能会遇到一个问题，即我们需要从字符串中删除作为字典关键字一部分的所有单词。这个问题可以应用于诸如 web 开发和日常编程等领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用`split() + loop + replace()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 split()执行将字符串转换为单词列表的任务。然后，我们使用 replace()将字符串中的单词替换为空字符串。

```
# Python3 code to demonstrate working of 
# Remove Dictionary Key Words
# Using split() + loop + replace()

# initializing string
test_str = 'gfg is best for geeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing Dictionary
test_dict = {'geeks' : 1, 'best': 6}

# Remove Dictionary Key Words
# Using split() + loop + replace()
for key in test_dict:
    if key in test_str.split(' '):
        test_str = test_str.replace(key, "")

# printing result 
print("The string after replace : " + str(test_str)) 
```

**Output :**

```
The original string is : gfg is best for geeks
The string after replace : gfg is  for 

```