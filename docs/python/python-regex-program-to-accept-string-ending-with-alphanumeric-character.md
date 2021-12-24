# Python 正则表达式|接受以字母数字字符结束的字符串的程序

> 原文:[https://www . geesforgeks . org/python-regex-program-to-accept-string-以字母数字字符结尾/](https://www.geeksforgeeks.org/python-regex-program-to-accept-string-ending-with-alphanumeric-character/)

**先决条件:**[Python 中的正则表达式](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)
给定一个字符串，编写一个 Python 程序，检查给定的字符串是否仅以字母数字字符结尾。
**例:**

```
Input: ankitrai326
Output: Accept

Input: ankirai@
Output: Discard
```

在这个程序中，我们使用的是 *re 模块*的 search()方法。
**re.search() :** 这个方法要么返回 None(如果模式不匹配)，要么返回 re。包含字符串匹配部分信息的 MatchObject。此方法在第一次匹配后停止，因此这比提取数据更适合测试正则表达式。
*POSIX/C 语言环境中的字母数字字符*由 36 个不区分大小写的符号(a-z 和 0-9)或 62 个区分大小写的字符(A-Z、A-Z 和 0-9)组成。
我们来看看这个的 Python 程序:

## 蟒蛇 3

```
# Python program to accept string ending
# with only alphanumeric character.
# import re module

# re module provides support
# for regular expressions
import re

# Make a regular expression to accept string
# ending with alphanumeric character
regex = '[a-zA-z0-9]{content}apos;

# Define a function for accepting string
# ending with alphanumeric character
def check(string):

     # pass the regular expression
     # and the string in search() method
    if(re.search(regex, string)):
        print("Accept")

    else:
        print("Discard")

# Driver Code
if __name__ == '__main__' :

    # Enter the string
    string = "ankirai@"

    # calling run function
    check(string)

    string = "ankitrai326"
    check(string)

    string = "ankit."
    check(string)

    string = "geeksforgeeks"
    check(string)
```

**输出:**

```
Discard
Accept
Discard
Accept
```