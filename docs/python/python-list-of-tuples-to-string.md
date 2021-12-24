# Python |字符串元组列表

> 原文:[https://www . geesforgeks . org/python-元组到字符串列表/](https://www.geeksforgeeks.org/python-list-of-tuples-to-string/)

很多时候，我们会遇到需要在字符串之间执行相互转换的问题，在这些情况下，我们会遇到需要将元组列表转换为原始的逗号分隔字符串的问题。让我们讨论执行这项任务的某些方法。

**方法#1:使用`str() + strip()`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们只需将一个列表转换为字符串，并去掉列表的左方括号和右方括号，以呈现一个字符串。

```
# Python3 code to demonstrate working of
# List of tuples to String
# using str() + strip()

# initialize list
test_list = [(1, 4), (5, 6), (8, 9), (3, 6)]

# printing original list
print("The original list is : " + str(test_list))

# List of tuples to String
# using str() + strip()
res = str(test_list).strip('[]')

# printing result
print("Resultant string from list of tuple : " + res)
```

**Output :**

```
The original list is : [(1, 4), (5, 6), (8, 9), (3, 6)]
Resultant string from list of tuple : (1, 4), (5, 6), (8, 9), (3, 6)

```