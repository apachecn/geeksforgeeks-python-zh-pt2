# Python |删除字符串中的空格

> 原文:[https://www . geesforgeks . org/python-从字符串中删除空格/](https://www.geeksforgeeks.org/python-remove-spaces-from-a-string/)

给定一个字符串，编写一个 Python 程序来删除其中的所有空格。

**示例:**

```
Input :  g e e k
Output : geek

Input : Hello World
Output : HelloWorld

```

有多种方法可以删除字符串中的空格。第一种是幼稚方法，在本文中已经讨论过。但是在这里，我们将讨论 Python 特有的所有方法。

**方法#1 :** 使用`replace()`

使用 replace()函数，我们用无空格("")替换所有空白。

```
# Python3 code to remove whitespace
def remove(string):
    return string.replace(" ", "")

# Driver Program
string = ' g e e k '
print(remove(string))
```

**Output:**

```
geek

```

**方法 2 :** 使用`split()`和`join()`

首先我们使用`split()`函数返回字符串中的单词列表，使用 *sep* 作为分隔符字符串。然后，我们使用`join()`来连接可迭代。

```
# Python3 code to remove whitespace
def remove(string):
    return "".join(string.split())

# Driver Program
string = ' g e e k '
print(remove(string))
```

**Output:**

```
geek

```

**方法#3 :** 使用 Python 正则表达式

```
# Python3 code to remove whitespace
import re

def remove(string):
    pattern = re.compile(r'\s+')
    return re.sub(pattern, '', string)

# Driver Program
string = ' g e e k '
print(remove(string))
```

**Output:**

```
geek

```

**方法#4 :** 使用`translate()`

```
# Python code to remove whitespace
import string

def remove(string):
    return string.translate(None, ' \n\t\r')

# Driver Program
string = ' g e e k '
print(remove(string))
```

**Output:**

```
geek

```