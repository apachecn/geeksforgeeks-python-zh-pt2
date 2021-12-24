# Python–字符串中随机大写

> 原文:[https://www . geesforgeks . org/python-random-大写字母字符串/](https://www.geeksforgeeks.org/python-random-uppercase-in-strings/)

给定一个字符串，任务是编写一个 Python 程序，随机将其字符转换为大写。

**示例:**

```py
Input : test_str = 'geeksforgeeks'
Output : GeeksfORgeeks

Explanation : Random elements are converted to Upper case characters.

Input : test_str = 'gfg'
Output : GFg

Explanation : Random elements are converted to Upper case characters.
```

**方法一:使用** [**加入()**](https://www.geeksforgeeks.org/join-function-python/) **+** [**选择()**](https://www.geeksforgeeks.org/python-numbers-choice-function/) **+** [**上位()**](https://www.geeksforgeeks.org/isupper-islower-lower-upper-python-applications/)T18】+T20**下位()**

在这种情况下，我们在每个字符处使用 choice()执行选择大写的随机字符的任务。上()和下()分别执行上、下字符的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Random uppercase in Strings
# Using join() + choice() + upper() + lower()
from random import choice

# initializing string
test_str = 'geeksforgeeks'

# printing original string
print("The original string is : " + str(test_str))

# choosing from upper or lower for each character
res = ''.join(choice((str.upper, str.lower))(char) for char in test_str)

# printing result
print("Random Uppercased Strings : " + str(res))
```

**输出:**

```py
The original string is : geeksforgeeks
Random Uppercased Strings : gEEkSFoRgEeKS
```

**方法二:使用** [**地图()**](https://www.geeksforgeeks.org/python-map-function/) **+** [**选择()**](https://www.geeksforgeeks.org/python-numbers-choice-function/)**+**[**zip()**](https://www.geeksforgeeks.org/zip-in-python/)

在这种情况下，我们使用 map()对所有小写和大写字符串进行选择()。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Random uppercase in Strings
# Using map() + choice() + zip()
from random import choice

# initializing string
test_str = 'geeksforgeeks'

# printing original string
print("The original string is : " + str(test_str))

# choosing from upper or lower for each character
# extending logic to each character using map()
res = ''.join(map(choice, zip(test_str.lower(), test_str.upper())))

# printing result
print("Random Uppercased Strings : " + str(res))
```

**输出:**

```py
The original string is : geeksforgeeks
Random Uppercased Strings : geEkSFORgEEKS
```