# Python–拆分字符串忽略空格格式字符

> 原文:[https://www . geesforgeks . org/python-拆分-字符串-忽略-空格-格式化-字符/](https://www.geeksforgeeks.org/python-split-strings-ignoring-the-space-formatting-characters/)

给定一个字符串，拆分成单词，忽略空格格式字符，如\n，\t 等。

> **输入**:test _ str = ' geeks forgeeks \ n \ r \ nt \ t \ n \ t test \ r \ t for \ f \ vgeeks '
> **输出** : ['geeksforgeeks '，' best '，' for '，' geeks']
> **解释**:所有空格字符作为参数加入。
> 
> **输入**:test _ str = ' geeksforgeeks \ n \ r \ nt \ t \ n \ t \ t best '
> **输出** : ['geeksforgeeks '，' best']
> **解释**:所有空格字符作为参数加入。

**方法 1:使用 re.split()**

在这种情况下，我们使用由空格字符组成的适当正则表达式，并使用 split()对一组正则表达式字符执行拆分。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Split Strings ignoring Space characters
# Using re.split()
import re

# initializing string
test_str = 'geeksforgeeks\n\r\t\t\nis\t\tbest\r\tfor geeks'

# printing original string
print("The original string is : " + str(test_str))

# space regex with split returns the result
res = re.split(r'[\n\t\f\v\r ]+', test_str)

# printing result
print("The split string : " + str(res))
```

**输出:**

```py
The original string is : geeksforgeeks

is        best
    for geeks
The split string : ['geeksforgeeks', 'is', 'best', 'for', 'geeks']
```

**方法二:使用 split()**

默认情况下，split()函数在空格处拆分字符串。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Split Strings ignoring Space characters
# Using split()

# initializing string
test_str = 'geeksforgeeks\n\r\t\t\nis\t\tbest\r\tfor geeks'

# printing original string
print("The original string is : " + str(test_str))

# printing result
print("The split string : " + str(test_str.split()))
```

**输出:**

```py
The original string is : geeksforgeeks

is        best
    for geeks
The split string : ['geeksforgeeks', 'is', 'best', 'for', 'geeks']
```