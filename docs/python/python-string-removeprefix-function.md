# Python 字符串–remove prefix()函数

> 原文:[https://www . geesforgeks . org/python-string-remove prefix-function/](https://www.geeksforgeeks.org/python-string-removeprefix-function/)

在本文中，我们将使用 str.removeprefix(前缀，/)函数来移除前缀并返回字符串的其余部分。如果没有找到前缀字符串，则返回原始字符串。它是在 Python 3.9.0 版本中引入的。

**语法:**

```py
str.removeprefix(prefix, /)

```

**参数:**

```py
suffix- prefix string that we are checking for.

```

**返回值:**

返回字符串[len(前缀):]否则返回原始字符串的副本。

**代码:**

**例 1:**

## 蟒蛇 3

```py
# Python 3.9 code explaining 
# str.removeprefix()

s = 'GeeksforGeeks'

# prefix exists
print(s.removeprefix('Geeks'))
print(s.removeprefix('G'))

# whole string is a prefix
# it would print an empty string
print(s.removeprefix('GeeksforGeeks'))

# prefix doesn't exist
# whole string is returned
print(s.removeprefix('for'))
print(s.removeprefix('IT'))
print(s.removeprefix('forGeeks'))
```

**输出:**

```py
forGeeks
eeksforGeeks

GeeksforGeeks
GeeksforGeeks
GeeksforGeeks

```

**例 2:**

## 蟒蛇 3

```py
# Python 3.9 code explaining 
# str.removeprefix()

# String for removeprefix() 
# If prefix exists then 
# remove prefix from the string 
# otherwise return original string 

string1 = "Welcome to python 3.9"
print("Original String 1 : ", string1) 

# prefix exists 
result = string1.removeprefix("Welcome") 
print("New string : ", result) 

string2 = "Welcome Geek"
print("Original String 2 : ", string2) 

# prefix doesn't exist 
result = string2.removeprefix("Geek") 
print("New string : ", result)
```

**输出:**

```py
Original String 1 :  Welcome to python 3.9
New string :   to python 3.9
Original String 2 :  Welcome Geek
New string :  Welcome Geek

```