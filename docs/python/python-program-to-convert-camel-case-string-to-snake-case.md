# Python 程序将驼色案串转换为蛇纹案

> 原文:[https://www . geesforgeks . org/python-program-convert-camel-case-string-to-snake-case/](https://www.geeksforgeeks.org/python-program-to-convert-camel-case-string-to-snake-case/)

给定一个 camel 大小写的字符串，编写一个 Python 程序将给定的字符串从 camel 大小写转换成 snake 大小写。
**例:**

```py
Input : GeeksForGeeks
Output : geeks_for_geeks

Input : ThisIsInCamelCase
Output : this_is_in_camel_case
```

让我们看看完成这项任务的不同方法。
**方法#1 :** 天真方法
这是一个将骆驼格转换为蛇格的天真实现。首先，我们用一个空列表初始化一个变量“res”，并在它后面附加第一个字符(小写)。现在，每次我们遇到大写字母，我们都会在“res”后面加上“_”和字母(小写)，否则，只需加上字母。

## 蟒蛇 3

```py
# Python3 program to convert string
# from camel case to snake case

def change_case(str):
    res = [str[0].lower()]
    for c in str[1:]:
        if c in ('ABCDEFGHIJKLMNOPQRSTUVWXYZ'):
            res.append('_')
            res.append(c.lower())
        else:
            res.append(c)

    return ''.join(res)

# Driver code
str = "GeeksForGeeks"
print(change_case(str))
```

**Output:** 

```py
geeks_for_geeks
```