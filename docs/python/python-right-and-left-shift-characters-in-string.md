# Python–字符串中的左右移位字符

> 原文:[https://www . geesforgeks . org/python-左右移位字符串中的字符/](https://www.geeksforgeeks.org/python-right-and-left-shift-characters-in-string/)

有时，在使用 Python 字符串时，我们会遇到这样的问题，即字符串中的字符左右旋转计数，并且想要知道字符串的结果条件。这类问题出现在竞争性编程中。让我们讨论执行这项任务的某些方法。

**方法#1:使用字符串乘法+字符串切片**
以上功能的组合可以用来执行这个任务。在这种情况下，我们三次多重字符串，执行连接和选择性切片字符串，以获得所需的结果。

```py
# Python3 code to demonstrate working of 
# Right and Left Shift characters in String
# Using String multiplication + string slicing

# initializing string
test_str = 'geeksforgeeks'

# printing original string
print("The original string is : " + test_str)

# initializing right rot 
r_rot = 7

# initializing left rot 
l_rot = 3

# Right and Left Shift characters in String
# Using String multiplication + string slicing
res = (test_str * 3)[len(test_str) + r_rot - l_rot : 
                  2 * len(test_str) + r_rot - l_rot]

# printing result 
print("The string after rotation is : " + str(res)) 
```

**Output :**

```py
The original string is : geeksforgeeks
The string after rotation is : sforgeeksgeek

```