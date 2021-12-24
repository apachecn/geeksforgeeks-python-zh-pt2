# Python 程序验证字符串只包含字母、数字、下划线和破折号

> 原文:[https://www . geesforgeks . org/python-program-to-verify-a-string-only-contains-字母-数字-下划线-破折号/](https://www.geeksforgeeks.org/python-program-to-verify-that-a-string-only-contains-letters-numbers-underscores-and-dashes/)

**先决条件:**[Python 中的正则表达式](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)

给定一个字符串，我们必须找出该字符串是否包含任何字母、数字、下划线和破折号。它通常用于验证用户名和密码的有效性。**例如**用户有一个人的用户名字符串，用户不希望用户名有任何特殊字符，如@、$，等等。

让我们看看解决这个任务的不同方法:

**方法 1:** 使用**正则表达式。**

正则表达式库中有一个函数( **re** )为我们比较两个字符串。 **re.match(pattern，string)** 是一个返回一个对象的函数，要想知道一个匹配项是否被找到，我们必须将其类型转换为布尔值。

> **语法:**重新匹配(模式，字符串)
> 
> **参数:**
> 
> *   **图案:**要检查的图案
> *   **字符串:**要检查模式的字符串
> 
> **返回:**匹配对象

让我们看一个例子:

**例 1:**

## 蟒蛇 3

```py
# import library
import re

# make a pattern
pattern = "^[A-Za-z0-9_-]*{content}quot;

# input
string = "G33ks_F0r_Geeks"

# convert match object 
# into boolean values
state = bool(re.match(pattern, string))

print(state)
```

**输出:**

```py
True
```

**例 2:**

## 蟒蛇 3

```py
# import library
import re

print(bool(re.match("^[A-Za-z0-9_-]*{content}quot;,
                    'ValidString12-_')))

print(bool(re.match("^[A-Za-z0-9_-]*{content}quot;, 
                    'inv@lidstring')))
```

**输出:**

```py
True
False
```

**方法二:**使用**套。**

Set 是 Python 中内置的数据类型。我们正在使用集合的**[**issubset()**](https://www.geeksforgeeks.org/issubset-in-python/)**函数，如果一个集合中的所有字符都存在于给定的集合中，则该函数返回真，否则返回假。****

> ******语法:**set _ name . issubset(set)
> T3】参数:****
> 
> *   ******集合:**表示必须搜索子集的集合****
> 
> ******返回:**布尔值****

****我们来看一个例子:
**例子 1:******

## ****蟒蛇 3****

```py
**# create a set of allowed characters
allowed_chars = set(("0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ_-"))

# input string
string = "inv@lid"

# convert string into set of characters
validation = set((string))

# check condition
if validation.issubset(allowed_chars):
    print("True")

else:
    print ("False")**
```

******输出:******

```py
**False**
```

******例 2:******

## ****蟒蛇 3****

```py
**allowed_chars = set("0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ_-")

string = "__Val1d__"

validation = set((string))

if validation.issubset(allowed_chars):
    print("True")

else:
    print ("False")**
```

******输出:******

```py
**True**
```