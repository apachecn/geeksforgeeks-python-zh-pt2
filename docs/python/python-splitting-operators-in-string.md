# Python |在字符串中拆分运算符

> 原文:[https://www . geesforgeks . org/python-spliting-operators-in-string/](https://www.geeksforgeeks.org/python-splitting-operators-in-string/)

有时，我们有一个源字符串来进行某些数学计算，我们需要将数字和运算符拆分为单个元素的列表。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`re.split()`**
这个任务可以使用 Python regex 库提供的拆分功能来解决，Python regex 库有能力根据特定条件拆分字符串，在这种情况下是所有的数字和运算符。

```
# Python3 code to demonstrate working of
# Splitting operators in String
# Using re.split()
import re

# initializing string 
test_str = "15 + 22 * 3-4 / 2"

# printing original string 
print("The original string is : " + str(test_str))

# Using re.split()
# Splitting operators in String
res = re.split(r'(\D)', test_str)

# printing result 
print("The list after performing split functionality : " + str(res))
```

**Output :**

> 原字符串为:15+22*3-4/2
> 执行拆分功能后的列表:['15 '，'+'，' 22 '，' *，' 3 '，'-'，' 4 '，'/'，' 2']