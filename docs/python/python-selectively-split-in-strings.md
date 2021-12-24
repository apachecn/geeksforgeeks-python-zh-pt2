# Python–有选择地分成字符串

> 原文:[https://www . geesforgeks . org/python-选择性-字符串分割/](https://www.geeksforgeeks.org/python-selectively-split-in-strings/)

有时，在使用 Python 字符串时，我们可能不得不执行拆分。不是有时，正常的，取决于交付者，而是取决于编程结构，如元素、数字、单词等，并隔离它们。让我们讨论一下解决这个问题的方法。

**方法:使用`re.findall()`**
可以使用特定的正则表达式来执行该任务。在本文中，我们使用不同的元素，如数字、单词标点符号等来构造正则表达式。

```py
# Python3 code to demonstrate working of 
# Selective Split in Strings
# Using regex
import re

# initializing string
test_str = "print(\"geeks\");"

# printing original string
print("The original string is : " + test_str)

# Selective Split in Strings
# Using regex
res = re.findall('\d+\.\d+|\d+|\w+|[^a-zA-Z\s]', test_str)

# printing result 
print("The splitted string is : " + str(res)) 
```

**Output :**

```py
The original string is : print("geeks");
The splitted string is : ['print', '(', '"', 'geeks', '"', ')', ';']

```