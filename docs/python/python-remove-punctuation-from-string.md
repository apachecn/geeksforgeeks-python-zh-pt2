# Python |删除字符串中的标点符号

> 原文:[https://www . geesforgeks . org/python-从字符串中删除标点符号/](https://www.geeksforgeeks.org/python-remove-punctuation-from-string/)

在使用 Python 字符串时，我们经常会遇到一个问题，那就是我们需要从字符串中删除某些字符。这可以应用于数据科学领域的数据预处理以及日常编程。让我们讨论一下执行这项任务的某些方法。

**方法一:使用循环+标点符号串**

这是执行这项任务的粗暴方式。在这种情况下，我们使用一个包含标点符号的原始字符串来检查标点符号，然后我们构造一个字符串来删除这些标点符号。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Removing punctuations in string
# Using loop + punctuation string

# initializing string
test_str = "Gfg, is best : for ! Geeks ;"

# printing original string
print("The original string is : " + test_str)

# initializing punctuations string
punc = '''!()-[]{};:'"\,<>./?@#$%^&*_~'''

# Removing punctuations in string
# Using loop + punctuation string
for ele in test_str:
    if ele in punc:
        test_str = test_str.replace(ele, "")

# printing result
print("The string after punctuation filter : " + test_str)
```

**Output : **

```
The original string is : Gfg, is best : for ! Geeks ;
The string after punctuation filter : Gfg is best  for  Geeks 
```

**方法 2:使用正则表达式**

用标点符号替换的部分也可以使用正则表达式来执行。在本文中，我们使用某个正则表达式将所有标点符号替换为空字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Removing punctuations in string
# Using regex
import re

# initializing string
test_str = "Gfg, is best : for ! Geeks ;"

# printing original string
print("The original string is : " + test_str)

# Removing punctuations in string
# Using regex
res = re.sub(r'[^\w\s]', '', test_str)

# printing result
print("The string after punctuation filter : " + res)
```

**Output : **

```
The original string is : Gfg, is best : for ! Geeks ;
The string after punctuation filter : Gfg is best  for  Geeks 
```