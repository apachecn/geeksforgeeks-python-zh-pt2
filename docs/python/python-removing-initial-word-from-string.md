# Python |从字符串中删除首字

> 原文:[https://www . geesforgeks . org/python-remove-initial-word-from-string/](https://www.geeksforgeeks.org/python-removing-initial-word-from-string/)

在编程过程中，有时，我们会遇到这样一个问题，要求必须删除字符串中的第一个单词。这类问题很常见，人们应该知道解决这类问题的方法。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`split()`**
该任务可以使用`split`函数来执行，该函数执行单词的拆分并将字符串的第一个单词与整个单词分开。

```
# Python3 code to demonstrate working of
# Removing Initial word from string
# Using split()

# initializing string 
test_str = "GeeksforGeeks is best"

# printing original string 
print("The original string is : " + test_str)

# Using split()
# Removing Initial word from string
res = test_str.split(' ', 1)[1]

# printing result 
print("The string after omitting first word is : " + str(res))
```

**Output :**

```
The original string is : GeeksforGeeks is best
The string after omitting first word is : is best

```