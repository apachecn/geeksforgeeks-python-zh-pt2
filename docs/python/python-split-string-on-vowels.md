# Python–在元音上拆分字符串

> 原文:[https://www . geesforgeks . org/python-元音上拆分字符串/](https://www.geeksforgeeks.org/python-split-string-on-vowels/)

给定一个字符串，对元音进行拆分。

> **输入** : test_str = 'GFGaBst'
> **输出** : ['GFG '，' Bst']
> **解释** : a 是元音，分裂发生在那上面。
> **输入**:test _ str = ' gfgabstufforigeeks '
> **输出** : ['GFG '，' Bst '，' for '，' geeks']
> **解释** : a，u，I 都是元音，分裂就发生在那上面。

**方法:使用 regex() + split()**

在这里，我们使用正则表达式 split()接受多个字符来执行 split，传递元音列表，对字符串执行 split 操作。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Split String on vowels
# Using split() + regex
import re

# initializing strings
test_str = 'GFGaBste4oCS'

# printing original string
print("The original string is : " + str(test_str))

# splitting on vowels
# constructing vowels list
# and separating using | operator
res = re.split('a|e|i|o|u', test_str)

# printing result
print("The splitted string : " + str(res))
```

**Output**

```
The original string is : GFGaBste4oCS
The splitted string : ['GFG', 'Bst', '4', 'CS']
```