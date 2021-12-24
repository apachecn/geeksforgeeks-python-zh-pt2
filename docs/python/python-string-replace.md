# Python 字符串|替换()

> 原文:[https://www.geeksforgeeks.org/python-string-replace/](https://www.geeksforgeeks.org/python-string-replace/)

**replace()** 是 Python 编程语言中的一个内置函数，它返回一个字符串的副本，其中一个子字符串的所有出现都被另一个子字符串替换。

**语法:**

```py
string.replace(old, new, count)
```

**参数:**

> **old–**要替换的旧子串。
> **新–**新的子串，将替换旧的子串。
> **count–**想要用新的子串替换旧的子串的次数。(**可选** )

**返回值:**
它返回一个字符串的副本，其中一个子字符串的所有出现都被另一个子字符串替换。

**注:**

*   如果未指定计数，则旧子串的所有出现都被新子串替换。
*   此方法返回字符串的副本，即不改变原始字符串。

下面是演示 ***替换()*** 的代码:

**例 1:**

## 蟒蛇 3

```py
# Python3 program to demonstrate the
# use of replace() method 

string = "geeks for geeks geeks geeks geeks"

# Prints the string by replacing all
# geeks by Geeks
print(string.replace("geeks", "Geeks"))

# Prints the string by replacing only
# 3 occurrence of Geeks 
print(string.replace("geeks", "GeeksforGeeks", 3))
```

**输出:**

```py
Geeks for Geeks Geeks Geeks Geeks
GeeksforGeeks for GeeksforGeeks GeeksforGeeks geeks geeks
```

**例 2:**

## 蟒蛇 3

```py
# Python3 program to demonstrate the
# use of replace() method

string = "geeks for geeks geeks geeks geeks"

# Prints the string by replacing
# e by a
print(string.replace("e", "a"))

# Prints the string by replacing only
# 3 occurrence of ek by a
print(string.replace("ek", "a", 3))
```

**输出:**

```py
gaaks for gaaks gaaks gaaks gaaks
geas for geas geas geeks geeks
```