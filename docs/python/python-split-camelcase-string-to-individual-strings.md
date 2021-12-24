# Python |将 CamelCase 字符串拆分为单个字符串

> 原文:[https://www . geesforgeks . org/python-split-camel case-string-to-individual-string/](https://www.geeksforgeeks.org/python-split-camelcase-string-to-individual-strings/)

给定一个 camel 大小写的字符串，编写一个 Python 程序将 camel 大小写字符串中的每个单词拆分成单独的字符串。

**示例:**

```
Input : "GeeksForGeeks"
Output : ['Geeks', 'For', 'Geeks']

Input : "ThisIsInCamelCase"
Output : ['This', 'Is', 'In', 'Camel', 'Case']

```

**方法#1 :** 天真方法

将 CamelCase 字符串拆分为单个字符串的一种简单或暴力的方法是使用*进行*循环。首先，使用一个空的“单词”列表，并将“str”的第一个字母附加在上面。现在对循环使用*，检查当前字母是否为小写，如果是，将其追加到当前字符串，否则，如果是大写，则开始新的单个字符串。*

```
# Python3 program Split camel case 
# string to individual strings

def camel_case_split(str):
    words = [[str[0]]]

    for c in str[1:]:
        if words[-1][-1].islower() and c.isupper():
            words.append(list(c))
        else:
            words[-1].append(c)

    return [''.join(word) for word in words]

# Driver code
str = "GeeksForGeeks"
print(camel_case_split(str))
```

**Output:**

```
['Geeks', 'For', 'Geeks']

```

**方法 2 :** 使用`enumerate`和`zip()`

在这个方法中，我们首先使用 Python 枚举来查找索引，新字符串从这里开始，并将它们保存在‘start _ idx’中。最后使用‘start _ idx’我们使用 Python *zip* 返回每个单独的字符串。

```
# Python3 program Split camel case 
# string to individual strings

import re

def camel_case_split(str):

    start_idx = [i for i, e in enumerate(str)
                 if e.isupper()] + [len(str)]

    start_idx = [0] + start_idx
    return [str[x: y] for x, y in zip(start_idx, start_idx[1:])] 

# Driver code
str = "GeeksForGeeks"
print(camel_case_split(str))
```

**Output:**

```
['', 'Geeks', 'For', 'Geeks']

```

**方法#3 :** 使用 Python 正则表达式

```
# Python3 program Split camel case 
# string to individual strings
import re

def camel_case_split(str):

    return re.findall(r'[A-Z](?:[a-z]+|[A-Z]*(?=[A-Z]|$))', str)

# Driver code
str = "GeeksForGeeks"
print(camel_case_split(str))
```

**Output:**

```
['Geeks', 'For', 'Geeks']

```