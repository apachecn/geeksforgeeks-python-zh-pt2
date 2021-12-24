# Python 程序在列表中查找字符串

> 原文:[https://www . geesforgeks . org/python-program-to-find-the-string-in-a-list/](https://www.geeksforgeeks.org/python-program-to-find-the-string-in-a-list/)

给定一个列表，任务是编写一个 Python 程序来检查列表是否包含特定的字符串。

**示例:**

> **输入** : l=[1，1.0，'有'，'一'，'极客'，'日']；s= '极客'
> 
> **输出:**极客出现在列表中
> 
> **输入:** l=['hello '，' geek '，' have '，' a '，' geek '，' day ']；s= '不错'
> 
> **输出:** nice 不在列表中

**方法#1:** 使用运算符中的

运算符中的*用于检查列表中是否存在特定的字符串/元素。*

**示例:**

## 蟒蛇 3

```py
# assign list
l = [1, 2.0, 'have', 'a', 'geeky', 'day']

# assign string
s = 'geeky' 

# check if string is present in the list
if s in l:
    print(f'{s} is present in the list')
else:
    print(f'{s} is not present in the list')
```

**输出:**

```py
geeky is present in the list
```

**方法 2:** 使用[计数()](https://www.geeksforgeeks.org/python-string-count/)功能

*count()* 函数用于统计列表中特定字符串的出现次数。如果一个字符串的计数大于 0，这意味着列表中存在特定的字符串，否则列表中不存在该字符串。

**示例:**

## 蟒蛇 3

```py
# assign list
l = ['1', 1.0, 32, 'a', 'geeky', 'day']

# assign string
s = 'prime'

# check if string is present in list
if l.count(s) > 0:
    print(f'{s} is present in the list')
else:
    print(f'{s} is not present in the list')
```

**输出:**

```py
prime is not present in the list
```

**方法 3:** 使用[列表理解](https://www.geeksforgeeks.org/python-list-comprehension/)

列表理解用于从元组、字符串、数组、列表等其他项创建新列表。它用于将迭代语句转换为公式。

**示例:**

## 蟒蛇 3

```py
# assign list
l = ['hello', 'geek', 'have', 'a', 'geeky', 'day']

# assign string
s = 'geek'

# list comprehension
compare = [i for i in l if s in l]

# check if sting is present in list
if len(compare) > 0:
    print(f'{s} is present in the list')
else:
    print(f'{s} is not present in the list')
```

**输出:**

```py
geeky is present in the list
```

**方法#4:** 使用[任意()](https://www.geeksforgeeks.org/python-any-function/)功能

*any()* 功能用于检查列表中是否存在元素。就像-如果字符串中的任何元素与输入元素匹配，打印该元素在列表中，否则，打印该元素不在列表中。

**示例:**

## 蟒蛇 3

```py
# assign list
l = ['hello', 'geek', 'have', 'a', 'geeky', 'day']

# assign string
s = 'prime'

# check if string is present in list
if any(s in i for i in l):
    print(f'{s} is present in the list')
else:
    print(f'{s} is not present in the list')
```

**输出:**

```py
prime is not present in the list
```