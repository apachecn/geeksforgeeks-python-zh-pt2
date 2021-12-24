# Python 字符串| rpartition()

> 原文:[https://www.geeksforgeeks.org/python-string-rpartition/](https://www.geeksforgeeks.org/python-string-rpartition/)

***【rpartition()】***函数在 Python 中将给定的字符串分成三部分。rpartition()从右侧开始寻找分隔符，直到找到分隔符，并返回一个元组，该元组包含分隔符前的部分字符串、字符串的参数和分隔符后的部分。

**语法:**

```py
string.rpartition(separator)
```

**参数:**

```py
separator -  separates the string at the first occurrence of it.
```

**返回值:**

1.  Returns the part of the string before the delimiter, the delimiter parameter itself, and the part after the delimiter if the delimiter parameter is found in the string.
2.  Returns two empty strings, or the given string if the separator cannot be found in the string.

**例外:**

```py
If separator argument is not supplied, it will throw TypeError.
```

**代码#1 :**

## 蟒蛇 3

```py
# Python3 code explaining rpartition()

# String need to split
string1 = "Geeks@for@Geeks@is@for@geeks"

string2 = "Ram is not eating but Mohan is eating"

# Here '@' is a separator
print(string1.rpartition('@'))

# Here 'is' is separator
print(string2.rpartition('is'))
```

**输出:**

```py
('Geeks@for@Geeks@is@for', '@', 'geeks')
('Ram is not eating but Mohan ', 'is', ' eating')
```

**代码#2 :**

## 蟒蛇 3

```py
# Python3 code explaining rpartition()

# String need to split
string = "Sita is going to school"

# Here 'not' is a separator which is not
# present in the given string
print(string.rpartition('not'))
```

**输出:**

```py
('', '', 'Sita is going to school')
```

**代码#3 :** 类型错误

## python 3

```py
# Python3 code explaining TypeError
# in rpartition()

str = "Bruce Waine is Batman"

# Nothing is passed as separator
print(str.rpartition())
```

**输出:**

```py
Traceback (most recent call last):
  File "/home/e207c003f42055cf9697001645999d69.py", line 7, in 
    print(str.rpartition())
TypeError: rpartition() takes exactly one argument (0 given)
```

**代码#4 :** 值错误

## python 3

```py
# Python3 code explaining ValueError
# in rpartition()

str = "Bruce Waine is Batman"

# Nothing is passed as separator
print(str.rpartition(""))
```

**输出:**

```py
Traceback (most recent call last):
  File "/home/c8d9719625793f2c8948542159719007.py", line 7, in 
    print(str.rpartition(""))
ValueError: empty separator
```