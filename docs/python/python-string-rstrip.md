# Python 字符串 rstrip()方法

> 原文:[https://www.geeksforgeeks.org/python-string-rstrip/](https://www.geeksforgeeks.org/python-string-rstrip/)

Python String **rstrip()** 方法返回字符串的副本，并删除尾随字符(基于传递的字符串参数)。如果没有传递参数，它将删除尾随空格。

> **语法:**
> 
> string.rstrip([chars])
> 
> **参数:**
> 
> 字符(可选)–指定要删除的字符集的字符串。
> 
> **返回:**
> 
> 返回字符串的副本，去掉尾部字符

### 例 1

## 蟒蛇 3

```py
# Python3 program to demonstrate the use of
# rstrip() method using optional parameters

# string which is to be stripped
string = "geekssss"

# Removes given set of characters from
# right.
print(string.rstrip('s'))
```

**输出:**

```py
geek
```

### 例 2

## 蟒蛇 3

```py
# Python3 program to demonstrate the use of
# rstrip() method using optional parameters

# string which is to be stripped
string = "   for    "

# Leading whitespaces are removed
print("Geeks" + string.rstrip() + " Geeks ")
```

**输出:**

```py
Geeks   for Geeks
```

### 例 3

## 蟒蛇 3

```py
# string which is to be stripped
string = "geeks for geeks"

# Argument doesn't contain trailing 's'
# So, no characters are removed
print(string.rstrip('ek'))
```

**输出:**

```py
geeks for geeks
```

### 例 4

## 蟒蛇 3

```py
# string which is to be stripped
string = "geeks for geeks"

# Removes given set of characters from
# right.
print(string.rstrip('ske'))
```

**输出:**

```py
geeks for g
```