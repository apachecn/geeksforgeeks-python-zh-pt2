# Python–通过分隔符进行子串连接

> 原文:[https://www . geesforgeks . org/python-substring-按分隔符串联/](https://www.geeksforgeeks.org/python-substring-concatenation-by-separator/)

有时，在使用 Python 列表时，我们可能会遇到这样的问题:我们需要在列表中执行字符串的连接，直到分隔符。这可以应用于我们需要分块数据的领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是可以执行该任务的蛮力方式。在这种情况下，我们执行连接循环条件语句的任务，并在分隔符出现时重新初始化字符串为空。

```py
# Python3 code to demonstrate working of 
# Substring concatenation by Separator
# Using loop

# initializing list
test_list = ['gfg', 'is', '*', 'best', '*', 'for', 'geeks']

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = '*'

# Substring concatenation by Separator
# Using loop
res = []
temp = ''
for sub in test_list:
    if sub != '*':
        temp += sub
    else:
        res.append(temp)
        temp = ''
if temp:
    res.append(temp)

# printing result 
print("The list after String concatenation : " + str(res)) 
```

**Output :**

```py
The original list is : ['gfg', 'is', '*', 'best', '*', 'for', 'geeks']
The list after String concatenation : ['gfgis', 'best', 'forgeeks']

```