# Python |从给定字符串中删除数字的方法

> 原文:[https://www . geesforgeks . org/python-从给定字符串中删除数字的方法/](https://www.geeksforgeeks.org/python-ways-to-remove-numeric-digits-from-given-string/)

给定一个字符串(可能包含字符和数字)，编写一个 Python 程序从字符串中删除数字。

让我们讨论一下完成这项任务的不同方法。

**方法一:使用`join`和`isdigit()`**

```py
# Python code to demonstrate
# how to remove numeric digits from string
# using join and isdigit

# initialising string
ini_string = "Geeks123for127geeks"

# printing initial ini_string
print("initial string : ", ini_string)

# using join and isdigit 
# to remove numeric digits from string
res = ''.join([i for i in ini_string if not i.isdigit()])

# printing result
print("final string : ", res)
```

**Output:**

```py
initial string :  Geeks123for127geeks
final string :  Geeksforgeeks

```

**方法 2:使用翻译和数字**

```py
# Python code to demonstrate
# how to remove numeric digits from string
# using translate
from string import digits

# initialising string
ini_string = "Geeks123for127geeks"

# printing initial ini_string
print("initial string : ", ini_string)

# using translate and digits
# to remove numeric digits from string
remove_digits = str.maketrans('', '', digits)
res = ini_string.translate(remove_digits)

# printing result
print("final string : ", res)
```

**Output:**

```py
initial string :  Geeks123for127geeks
final string :  Geeksforgeeks

```

**方法三:使用 `filter`和λ**

```py
# Python code to demonstrate
# how to remove numeric digits from string
# using filter and lambda

# initialising string
ini_string = "akshat123garg"

# printing initial ini_string
print("initial string : ", ini_string)

# using filter and lambda
# to remove numeric digits from string
res = "".join(filter(lambda x: not x.isdigit(), ini_string))

# res = ini_string
# printing result
print("final string : ", str(res))
```

**Output:**

```py
initial string :  akshat123garg
final string :  akshatgarg

```