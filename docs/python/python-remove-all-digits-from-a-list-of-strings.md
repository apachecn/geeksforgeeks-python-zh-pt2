# Python |删除字符串列表中的所有数字

> 原文:[https://www . geesforgeks . org/python-从字符串列表中删除所有数字/](https://www.geeksforgeeks.org/python-remove-all-digits-from-a-list-of-strings/)

给定一个字符串列表，编写一个 Python 程序从字符串列表中删除所有数字。

**示例:**

```py
Input : ['alice1', 'bob2', 'cara3']
Output : ['alice', 'bob', 'cara']

Input : ['4geeks', '3for', '4geeks']
Output : ['geeks', 'for', 'geeks']

```

**方法#1 :** Python 正则表达式

Python regex 模式也可以用来查找每个字符串是否包含数字，并将其转换为" "。

```py
# Python program to Remove all 
# digits from a list of string
import re

def remove(list):
    pattern = '[0-9]'
    list = [re.sub(pattern, '', i) for i in list]
    return list

# Driver code 

list = ['4geeks', '3for', '4geeks']
print(remove(list))
```

**Output:**

```py
['geeks', 'for', 'geeks']

```

**方法#2 :** 使用`**str.maketrans()**`方法
`maketrans()`方法返回一个翻译表，将输入字符串中的每个字符映射到输出字符串中相同位置的字符。在这个特殊的问题中，我们将每个数字翻译成“用于循环”。

```py
# Python program to Remove all 
# digits from a list of string
from string import digits

def remove(list):
    remove_digits = str.maketrans('', '', digits)
    list = [i.translate(remove_digits) for i in list]
    return list

# Driver code 

list = ['4geeks', '3for', '4geeks']
print(remove(list))
```

**Output:**

```py
['geeks', 'for', 'geeks']

```

**方法#3 :** 使用`**str.isalpha()**`方法
在这种方法中，我们使用两个循环来检查字符串的字符是否是字母表。如果是，就把它加入列表，否则就离开它。

```py
# Python program to Remove all 
# digits from a list of string
from string import digits

def remove(list):
    list = [''.join(x for x in i if x.isalpha()) for i in list]

    return list

# Driver code 

list = ['4geeks', '3for', '4geeks']
print(remove(list))
```

**Output:**

```py
['geeks', 'for', 'geeks']

```