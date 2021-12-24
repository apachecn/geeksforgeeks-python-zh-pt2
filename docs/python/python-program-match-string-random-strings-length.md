# 生成随机字符串，直到生成给定的字符串

> 原文:[https://www . geesforgeks . org/python-program-match-string-random-strings-length/](https://www.geeksforgeeks.org/python-program-match-string-random-strings-length/)

给定字符串，任务是使用特殊字符、数字和字母的随机组合生成相同的字符串。

示例:

```
Input : GFG
Output :n4W
        mK7
        k1x
        q;;, !g
        .
        .
        .
        .
        .
        GF,
        GFf
        GFp
        GFG

Target matched after 167 iterations

```

先决条件:[在 Python 中生成随机标识](https://www.geeksforgeeks.org/generating-random-ids-python/)

`string.ascii_lowercase`、`string.digits`、`string.ascii_uppercase`是 Python 中字符串模块中常见的一些字符串常量，这里作为字典使用。所有这些字符串常量都与其他特殊字符(如**)组合在一起。, !？；:'**和都存储在变量中。

**方法:**简单运行两个循环，使用 python 提供的随机函数。它将显示随机函数可以提供的所有可能的组合，同样的事情将由解密循环完成。最后，当提示输入时，它将显示与您插入的文本相同的文本。它会将每个随机字符串与给定的字符串进行匹配。如果两个索引都匹配，则修复该索引，并对剩余的索引进行迭代。
T3】下面是实现:

```
# Python program to generate and match 
# the string from all random strings
# of same length

# Importing string, random
# and time modules
import string
import random
import time

# all possible characters including 
# lowercase, uppercase and special symbols
possibleCharacters = string.ascii_lowercase + string.digits + 
                     string.ascii_uppercase + ' ., !?;:'

# string to be generated
t = "geek"

# To take input from user
# t = input(str("Enter your target text: "))

attemptThis = ''.join(random.choice(possibleCharacters)
                                for i in range(len(t)))
attemptNext = ''

completed = False
iteration = 0

# Iterate while completed is false
while completed == False:
    print(attemptThis)

    attemptNext = ''
    completed = True

    # Fix the index if matches with 
    # the strings to be generated
    for i in range(len(t)):
        if attemptThis[i] != t[i]:
            completed = False
            attemptNext += random.choice(possibleCharacters)
        else:
            attemptNext += t[i]

    # increment the iteration 
    iteration += 1
    attemptThis = attemptNext
    time.sleep(0.1)

# Driver Code
print("Target matched after " +
      str(iteration) + " iterations")
```

**输出:**

```
FyFJ
.:YZ
aubo
.
.
.
g56G
gk6R
g7Se
gT o
gD d
gXek
g0ek
g ek
.
. 
gUek
giek
geek

Target matched after 168 iterations
```