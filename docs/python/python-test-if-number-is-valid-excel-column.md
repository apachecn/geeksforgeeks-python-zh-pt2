# Python |测试数字是否有效 Excel 列

> 原文:[https://www . geesforgeks . org/python-test-if-number-valid-excel-column/](https://www.geeksforgeeks.org/python-test-if-number-is-valid-excel-column/)

有时，在使用 Python 字符串时，我们会遇到一个问题，即我们需要测试字符串是否是有效的 excel 列。这在许多领域都有应用，包括日常编程、网络开发和数据科学。让我们讨论执行这项任务的特定方式。

**方法:使用`re.match() + group()`**
以上功能的组合可以用来执行此任务。在这种情况下，我们执行 regex match()来匹配具有 A-XDF 的可能更新的 excel 版本，并以 0-9 开头，后跟不超过 1048576 的 0-6 个字符。groupby()用于在此基础上对元素进行分组。

```py
# Python3 code to demonstrate working of 
# Test if number is valid Excel column
# Using re.match() + groupby()
import re

# initializing string
test_str = "C101"

# printing original string
print("The original string is : " + test_str)

# Test if number is valid Excel column
# Using re.match() + groupby()
temp = re.match(r'^([A-Z]{1, 2}|[A-W][A-Z]{2}|X[A-E][A-Z]|XF[A-D])([1-9]\d{0, 6}){content}apos;, test_str)
res = bool(temp) and int(temp.group(2)) < 1048577

# printing result 
print("Is string valid excel column : " + str(res)) 
```

**Output :**

```py
The original string is : C101
Is string valid excel column : True

```