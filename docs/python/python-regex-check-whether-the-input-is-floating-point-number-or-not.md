# Python 正则表达式|检查输入是否为浮点数

> 原文:[https://www . geeksforgeeks . org/python-regex-check-输入是否为浮点数/](https://www.geeksforgeeks.org/python-regex-check-whether-the-input-is-floating-point-number-or-not/)

**先决条件:**[Python 中的正则表达式](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)

给定一个输入，编写一个 Python 程序来检查给定的输入是否是浮点数。

**示例:**

```
Input:  1.20
Output: Floating point number

Input: -2.356
Output: Floating point number

Input: 0.2
Output: Floating point number

Input: -3
Output: Not a Floating point number

```

在这个程序中，我们使用的是 **`search()`** 法的 *re 模块*。

**re.search() :** 这个方法要么返回 None(如果模式不匹配)，要么返回包含字符串匹配部分信息的`re.MatchObject`。此方法在第一次匹配后停止，因此这比提取数据更适合测试正则表达式。

让我们看看 Python 程序:

```
# Python program to check input is
# Floating point number or not

# import re module

# re module provides support
# for regular expressions
import re

# Make a regular expression for
# identifying Floating point number 
regex = '[+-]?[0-9]+\.[0-9]+'

# Define a function to
# check Floating point number 
def check(floatnum): 

     # pass the regular expression
     # and the string in search() method
    if(re.search(regex, floatnum)): 
        print("Floating point number") 

    else: 
        print("Not a Floating point number") 

# Driver Code 
if __name__ == '__main__' : 

    # Enter the floating point number
    floatnum = "1.20"

    # calling run function 
    check(floatnum)

    floatnum = "-2.356"
    check(floatnum)

    floatnum = "0.2"
    check(floatnum)

    floatnum = "-3"
    check(floatnum)
```

**Output:**

```
Floating point number
Floating point number
Floating point number
Not a Floating point number

```