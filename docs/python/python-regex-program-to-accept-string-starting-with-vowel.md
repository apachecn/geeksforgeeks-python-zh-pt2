# Python Regex–接受以元音开头的字符串的程序

> 原文:[https://www . geesforgeks . org/python-regex-program-to-accept-string-以元音开头/](https://www.geeksforgeeks.org/python-regex-program-to-accept-string-starting-with-vowel/)

**先决条件:**[Python 中的正则表达式](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)
给定一个字符串，编写 Python 程序检查给定的字符串是否以元音开头。
**例:**

```py

Input: animal
Output: Accepted

Input: zebra
Output: Not Accepted
```

在这个程序中，我们使用的是 *re 模块*的 search()方法。
**re.search()** :这个方法要么返回 None(如果模式不匹配)，要么返回 re。包含字符串匹配部分信息的 MatchObject。此方法在第一次匹配后停止，因此这比提取数据更适合测试正则表达式。
我们来看看这个的 Python 程序:

## 蟒蛇 3

```py
# Python program to accept string starting with a vowel

# import re module

# re module provides support
# for regular expressions
import re

# Make a regular expression
# to accept string starting with vowel
regex = '^[aeiouAEIOU][A-Za-z0-9_]*'

# Define a function for
# accepting string start with vowel
def check(string):

     # pass the regular expression
     # and the string in search() method
    if(re.search(regex, string)):
        print("Valid")

    else:
        print("Invalid")

# Driver Code
if __name__ == '__main__' :

    # Enter the string
    string = "ankit"

    # calling run function
    check(string)

    string = "geeks"
    check(string)

    string = "sandeep"
    check(string)
```

**Output:** 

```py
Valid
Invalid
Invalid
```