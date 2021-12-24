# 蟒蛇串上()

> 原文:[https://www.geeksforgeeks.org/python-string-upper/](https://www.geeksforgeeks.org/python-string-upper/)

**upper()** 方法将字符串中的所有小写字符转换为大写字符并返回

**语法:**

```py
string.upper()

```

**参数:**

> `upper()`方法不取任何参数。

**返回:**

```py
returns a uppercased string of the given string

```

**代码 1:** 仅包含字母字符的字符串

```py
# Python3 program to show the
# working of upper() function
text = 'geeKs For geEkS'

print("Original String:")
print(text)

# upper() function to convert 
# string to upper_case
print("\nConverted String:")
print(text.upper())
```

**输出:**

```py
Original String:
geeKs For geEkS

Converted String:
GEEKS FOR GEEKS
```

**代码 2:** 带字母数字字符的字符串

```py
# Python3 program to show the
# working of upper() function
text = 'g3Ek5 f0r gE3K5'

print("Original String:")
print(text)

# upper() function to convert 
# string to upper_case
print("\nConverted String:")
print(text.upper())
```

**输出:**

```py
Original String:
g3Ek5 f0r gE3K5

Converted String:
G3EK5 F0R GE3K5

```

**应用:**upper()方法的常见应用之一是检查两个字符串是否相同

```py
# Python3 program to show the
# working of upper() function
text1 = 'geeks fOr geeks'

text2 = 'gEeKS fOR GeeKs'

# Comparison of strings using 
# upper() method
if(text1.upper() == text2.upper()):
    print("Strings are same")
else: 
    print("Strings are not same")
```

**输出:**

```py
Strings are same
```