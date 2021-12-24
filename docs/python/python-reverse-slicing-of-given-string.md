# Python |给定字符串的反向切片

> 原文:[https://www . geesforgeks . org/python-给定字符串的反向切片/](https://www.geeksforgeeks.org/python-reverse-slicing-of-given-string/)

有时候，在处理字符串时，我们可能会遇到一个问题，我们需要对字符串执行反向切片，即从后端为某些字符对字符串进行切片。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`join() + reversed()`**
上述功能的组合可用于执行该特定任务。在这种情况下，我们在内存中反转字符串，并加入切片的字符数，以便从后端返回切片的字符串。

```py
# Python3 code to demonstrate working of
# Reverse Slicing string 
# Using join() + reversed()

# initializing string 
test_str = "GeeksforGeeks"

# printing original string 
print("The original string is : " + test_str)

# initializing K 
K = 7

# Using join() + reversed()
# Reverse Slicing string 
res = ''.join(reversed(test_str[0:K]))

# printing result 
print("The reversed sliced string is : " + res)
```

**Output :**

```py
The original string is : GeeksforGeeks
The reversed sliced string is : ofskeeG

```