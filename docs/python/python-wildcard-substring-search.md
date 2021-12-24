# Python–通配符子串搜索

> 原文:[https://www . geesforgeks . org/python-通配符-子串-搜索/](https://www.geeksforgeeks.org/python-wildcard-substring-search/)

有时候，在使用 Python Strings 时，我们会遇到一个问题，我们需要搜索子字符串，但是缺少一些字符，我们需要找到匹配的。这在许多领域都有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`re.search()`**
这是可以执行这个任务的方式之一。在本例中，我们使用子字符串来填充正则表达式编译，并使用 search()中的 main string 来搜索它。

```py
# Python3 code to demonstrate working of 
# Wildcard Substring search
# Using re.search()
import re

# initializing string
test_str = 'geeksforgeeks is best for geeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing Substring
sub_str = '..st'

# Wildcard Substring search
# Using re.search()
temp = re.compile(sub_str) 
res = temp.search(test_str)

# printing result 
print("The substring match is : " + str(res.group(0))) 
```

**Output :**

```py
The original string is : geeksforgeeks is best for geeks                                                                
The substring match is : best     

```