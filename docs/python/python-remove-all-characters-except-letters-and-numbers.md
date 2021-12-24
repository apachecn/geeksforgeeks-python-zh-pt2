# Python |删除除字母和数字以外的所有字符

> 原文:[https://www . geesforgeks . org/python-移除除字母和数字以外的所有字符/](https://www.geeksforgeeks.org/python-remove-all-characters-except-letters-and-numbers/)

给定一个字符串，任务是删除除数字和字母之外的所有字符。

字符串操作是日常编码和 web 开发中非常重要的任务。HTTP 查询中的大多数请求和响应都是字符串形式的，有时会有一些无用的数据需要我们删除。让我们讨论一些去除除数字和字母之外的所有字符的 Pythonic 方法。

**方法一:使用 [`re.sub`](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)**

```py
# Python code to demonstrate
# to remove all the characters
# except numbers and alphabets

import re

# initialising string
ini_string = "123abcjw:, .@! eiw"

# printing initial string
print ("initial string : ", ini_string)

# function to demonstrate removal of characters
# which are not numbers and alphabets using re

result = re.sub('[\W_]+', '', ini_string)

# printing final string
print ("final string", result)
```

**Output:**

```py
initial string :  123abcjw:, .@! eiw
final string 123abcjweiw

```

**方法 2:使用[伊萨法()](https://www.geeksforgeeks.org/python-string-isalpha-application/)和[伊斯默里克()](https://www.geeksforgeeks.org/python-string-isnumeric-application/)**

```py
# Python code to demonstrate
# to remove all the characters
# except numbers and alphabets

import re

# initialising string
ini_string = "123abcjw:, .@! eiw"

# printing initial string
print ("initial string : ", ini_string)

# function to demonstrate removal of characters
# which are not numbers and alphabets using re
getVals = list([val for val in ini_string
               if val.isalpha() or val.isnumeric()])

result = "".join(getVals)

# printing final string
print ("final string", result)
```

**Output:**

```py
initial string :  123abcjw:, .@! eiw
final string 123abcjweiw

```

**方法三:使用`[alnum()](https://www.geeksforgeeks.org/python-string-isalnum/)`**

```py
# Python code to demonstrate
# to remove all the characters
# except numbers and alphabets

# initialising string
ini_string = "123abcjw:, .@! eiw"

# printing initial string
print ("initial string : ", ini_string)

# function to demonstrate removal of characters
# which are not numbers and alphabets using re
getVals = list([val for val in ini_string if val.isalnum()])
result = "".join(getVals)

# printing final string
print ("final string", result)
```

**Output:**

```py
initial string :  123abcjw:, .@! eiw
final string 123abcjweiw

```