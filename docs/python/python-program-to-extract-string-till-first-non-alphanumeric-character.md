# Python 程序提取字符串直到第一个非字母数字字符

> 原文:[https://www . geesforgeks . org/python-程序提取-字符串-直到第一个-非字母数字字符/](https://www.geeksforgeeks.org/python-program-to-extract-string-till-first-non-alphanumeric-character/)

给定一个字符串，在第一次出现非字母数字之前提取所有字母数字。

> **输入** : test_str = 'geek$s4g！！！eeks'
> **输出**:极客
> **解释**:停在$出现。
> 
> **输入** : test_str = 'ge)eks4g！！！eeks'
> **输出** : ge
> **解释**:停止于)发生。

**方法#1:使用正则表达式+搜索()**

在这种情况下，search()用于在适当的 regex()中搜索字母数字，然后对结果进行切分，直到第一次出现非字母数字字符

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract string till first Non-Alphanumeric character
# Using regex + search()
import re

# initializing string
test_str = 'geeks4g!!!eeks'

# printing original string
print("The original string is : " + str(test_str))

# using start() to get 1st substring
res = re.search(r'\W+', test_str).start()
res = test_str[0 : res]

# printing result 
print("The resultant string : " + str(res))
```

**Output**

```
The original string is : geeks4g!!!eeks
The resultant string : geeks4g

```

**方法 2:使用 findall()**

这是解决这个问题的另一种正则表达式方法。在这种情况下，我们通过访问第 0 个索引来提取非 alnum 字符之前的第一个子字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract string till first Non-Alphanumeric character
# Using findall()
import re

# initializing string
test_str = 'geeks4g!!!eeks'

# printing original string
print("The original string is : " + str(test_str))

# using findall() to get all substrings 
# 0th index gives 1st substring
res = re.findall("[\dA-Za-z]*", test_str)[0]

# printing result 
print("The resultant string : " + str(res))
```

**Output**

```
The original string is : geeks4g!!!eeks
The resultant string : geeks4g

```