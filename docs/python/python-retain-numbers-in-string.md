# Python–将数字保留在字符串中

> 原文:[https://www . geesforgeks . org/python-retain-numbers-in-string/](https://www.geeksforgeeks.org/python-retain-numbers-in-string/)

有时，在使用 Python Strings 时，我们可能会遇到一个问题，即需要移除整数以外的所有字符。这类问题可以应用于许多数据领域，如机器学习和网络开发。让我们讨论执行这项任务的某些方法。

> **输入** : test_str = 'G4g 为 1 号'
> T3】输出 : 41
> 
> **输入** : test_str = 'Gfg 为 1 号'
> **输出** : 1

**方法#1:使用列表理解+ `join() + isdigit()`**
以上功能的组合可以用来解决这个问题。在本例中，我们使用 isdigit()执行提取整数的任务，使用列表理解进行迭代，使用 join()对过滤后的数字进行连接。

```
# Python3 code to demonstrate working of 
# Retain Numbers in String
# Using list comprehension + join() + isdigit()

# initializing string
test_str = 'G4g is No. 1 for Geeks 7'

# printing original string
print("The original string is : " + str(test_str))

# Retain Numbers in String
# Using list comprehension + join() + isdigit()
res = "".join([ele for ele in test_str if ele.isdigit()])

# printing result 
print("String after integer retention : " + str(res)) 
```

**Output :**

```
The original string is : G4g is No. 1 for Geeks 7
String after integer retention : 417

```

**方法 2:使用`regex()`**
使用正则表达式也可以找到问题的解决方案。在这种情况下，我们制定适当的正则表达式来从字符串中只过滤数字。

```
# Python3 code to demonstrate working of 
# Retain Numbers in String
# Using regex()
import re

# initializing string
test_str = 'G4g is No. 1 for Geeks 7'

# printing original string
print("The original string is : " + str(test_str))

# Retain Numbers in String
# Using regex()
res = re.sub(r'[^\d]+', '', test_str) 

# printing result 
print("String after integer retention : " + str(res)) 
```

**Output :**

```
The original string is : G4g is No. 1 for Geeks 7
String after integer retention : 417

```