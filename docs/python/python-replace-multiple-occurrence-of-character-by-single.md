# Python |用单个

替换字符的多次出现

> 原文:[https://www . geeksforgeeks . org/python-替换-单个字符多次出现/](https://www.geeksforgeeks.org/python-replace-multiple-occurrence-of-character-by-single/)

给定一个字符串和一个字符，编写一个 Python 程序，用一个字符替换给定字符的多次出现。

**示例:**

```py
Input : Geeksforgeeks, ch = 'e'
Output : Geksforgeks

Input : Wiiiin, ch = 'i'
Output : Win

```

**方法#1 :** 天真方法
这是一种蛮力方法，我们采用另一个列表‘new _ str’。使用 for 循环检查给定字符是否重复。如果重复多次，则将字符单次追加到列表中。其他字符(不是给定的字符)被简单地附加到列表中，没有任何改变。

```py
# Python program to replace multiple 
# occurrences of a character by a single character

def replace(s, ch):
    new_str = []
    l = len(s)

    for i in range(len(s)):
        if (s[i] == ch and i != (l-1) and
           i != 0 and s[i + 1] != ch and s[i-1] != ch):
            new_str.append(s[i])

        elif s[i] == ch:
            if ((i != (l-1) and s[i + 1] == ch) and
               (i != 0 and s[i-1] != ch)):
                new_str.append(s[i])

        else:
            new_str.append(s[i])

    return ("".join(i for i in new_str))

# Driver code 
s = 'Geeksforgeeks'
char = 'e'
print(replace(s, char))
```

**Output:**

```py
Geksforgeks

```

**方法 2 :** 使用 Python 正则表达式

```py
import re

# Function to replace multiple occurrences  
# of a character by a single character
def replace(string, char):
    pattern = char + '{2,}'
    string = re.sub(pattern, char, string)
    return string

# Driver code 
string = 'Geeksforgeeks'
char = 'e'
print(replace(string, char))
```

**Output:**

```py
Geksforgeks

```