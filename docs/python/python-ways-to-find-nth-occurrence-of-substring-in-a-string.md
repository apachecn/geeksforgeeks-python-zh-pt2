# Python |查找字符串中子串第 n 次出现的方法

> 原文:[https://www . geeksforgeeks . org/python-第 n 次出现字符串中的子字符串/](https://www.geeksforgeeks.org/python-ways-to-find-nth-occurrence-of-substring-in-a-string/)

给定一个字符串和一个子字符串，编写一个 Python 程序来查找该字符串的第 n 次出现。让我们讨论几个解决给定任务的方法。

**方法#1:使用 re**

```py
# Python code to demonstrate 
# to find nth occurrence of substring

import re

# Initialising values
ini_str = "abababababab"
substr = "ab"
occurrence = 4

# Finding nth occurrence of substring
inilist = [m.start() for m in re.finditer(r"ab", ini_str)]
if len(inilist)>= 4:

    # Printing result
    print ("Nth occurrence of substring at", inilist[occurrence-1])
else:
    print ("No {} occurrence of substring lies in given string".format(occurrence))
```

**方法 2:使用 find()方法**

```py
# Python code to demonstrate 
# to find nth occurrence of substring

# Initialising values
ini_str = "abababababab"
sub_str = "ab"
occurrence = 4

# Finding nth occurrence of substring
val = -1
for i in range(0, occurrence):
    val = ini_str.find(sub_str, val + 1)

# Printing nth occurrence
print ("Nth occurrence is at", val)
```

**方法三:使用 startswith()和列表理解**

```py
# Python code to demonstrate 
# to find nth occurrence of substring

# Initialising values
ini_str = "abababababab"
substr = "ab"
occurrence = 4

# Finding nth occurrence of substring
inilist = [i for i in range(0, len(ini_str))
            if ini_str[i:].startswith(substr)]

if len(inilist)>= 4:

    # Printing result
    print ("Nth occurrence of substring at", inilist[occurrence-1])
else:
    print ("No {} occurrence of substring lies in given string".format(occurrence))

```