# Python 程序测试字符串是否只有数字和字母

> 原文:[https://www . geeksforgeeks . org/python-仅测试字符串数字和字母的程序/](https://www.geeksforgeeks.org/python-program-to-test-if-the-string-only-numbers-and-alphabets/)

给定一个字符串，我们的任务是编写一个 Python 程序来检查字符串是否包含数字和字母，而不是数字或标点符号。

**示例:**

```py
Input : test_str = 'Geeks4Geeks'
Output : True
Explanation : Contains both number and alphabets.

Input : test_str = 'GeeksforGeeks'
Output : False
Explanation : Doesn't contain number.
```

**方法#1:使用**[**isalpha()**](https://www.geeksforgeeks.org/python-string-isalpha-application/)**+**[**is digit()**](https://www.geeksforgeeks.org/python-string-isdigit-application/)**+**[**any()**](https://www.geeksforgeeks.org/python-any-function/)**+**[T21】all()](https://www.geeksforgeeks.org/any-all-in-python/)**+**[**isalnum()**](https://www.geeksforgeeks.org/python-string-isalnum/)

在本例中，我们使用 all()，isalpha()和 isdigit()检查包含字母和数字组合的所有数字。any()和 isalnum()用于过滤标点符号的可能性。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Test if string contains both Numbers and Alphabets only
# Using isalpha() + isdigit() + any() + all() + isalnum()

# initializing string
test_str = 'Geeks4Geeks'

# printing original string
print("The original string is : " + str(test_str))

# conditional combination for getting result.
res = not ((all(idx.isdigit() for idx in test_str) or (all(idx.isalpha() 
            for idx in test_str)) or (any(not idx.isalnum() for idx in test_str))))

# printing result
print("Does string contain both numbers and alphabets only? : " + str(res))
```

**输出:**

```py
The original string is : Geeks4Geeks
Does string contain both numbers and alphabets only? : True
```

**方法 2:使用** [**regex**](https://www.geeksforgeeks.org/python-regex-re-search-vs-re-findall/)

使用正则表达式是解决这个问题的方法之一。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Test if string contains both Numbers and Alphabets only
# Using regex
import re

# initializing string
test_str = 'Geeks4Geeks'

# printing original string
print("The original string is : " + str(test_str))

# conditional combination for getting result.
res = bool(re.match("^(?=.*[a-zA-Z])(?=.*[\d])[a-zA-Z\d]+{content}quot;, "A530"))

# printing result
print("Does string contain both numbers and alphabets only? : " + str(res))
```

**输出:**

```py
The original string is : Geeks4Geeks
Does string contain both numbers and alphabets only? : True
```