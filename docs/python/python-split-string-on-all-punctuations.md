# Python–在所有标点符号上拆分字符串

> 原文:[https://www . geesforgeks . org/python-全标点符号拆分字符串/](https://www.geeksforgeeks.org/python-split-string-on-all-punctuations/)

给定一个字符串，在所有标点符号上拆分字符串。

> **输入** : test_str = 'geeksforgeeks！is-best '
> **Output**:[' geeksforgeeks '，'！'，' is '，'-'，' best']
> **解释**:劈叉开'！'和“-”。
> 
> **输入** : test_str = 'geek-sfo，rgeeks！is-best '
> **Output**:[' geek '，'-'，' sfo '，'，'，' rgeeks '，'！'，' is '，'-'，' best']
> **解释**:劈叉开'！'、“、”和“-”。

**方法:使用正则表达式+ findall()**

这是解决这个问题的一种方法。在本文中，我们构建了适当的正则表达式，分离和拆分任务由 findall()完成。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Split String on all punctuations
# using regex + findall()
import re

# initializing string
test_str = 'geeksforgeeks ! is-best, for @geeks'

# printing original String
print("The original string is : " + str(test_str))

# using findall() to get all regex matches. 
res = re.findall( r'\w+|[^\s\w]+', test_str)

# printing result 
print("The converted string : " + str(res)) 
```

**Output**

```
The original string is : geeksforgeeks! is-best, for @geeks
The converted string : ['geeksforgeeks', '!', 'is', '-', 'best', ', ', 'for', '@', 'geeks']

```