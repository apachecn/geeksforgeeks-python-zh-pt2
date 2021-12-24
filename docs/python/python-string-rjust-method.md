# Python 字符串 rjust()方法

> 原文:[https://www.geeksforgeeks.org/python-string-rjust-method/](https://www.geeksforgeeks.org/python-string-rjust-method/)

Python String rjust()方法在替换原始字符串左侧的给定字符后，返回给定长度的新字符串。

> **语法:**
> 
> string.rjust(长度，fillchar)
> 
> **参数:**
> 
> *   **长度**:修改后的字符串长度。如果长度小于或等于原始字符串的长度，则返回原始字符串。
> *   **fillchar** :(可选)需要填充的字符。如果没有提供，空间将作为默认参数。
> 
> **返回值:**
> 
> 在原始字符串左侧替换给定字符后，返回给定长度的新字符串。

### 例 1

## 蟒蛇 3

```py
# Python program to demonstrate working of
# rjust()
string = 'geeks'
length = 8

# If no fill character is provided, space
# is used as fill character
print(string.rjust(length))
```

**输出:**

```py
   geeks 
```

### 例 2

## 蟒蛇 3

```py
# example string
string = 'geeks'
length = 8
fillchar = '*'

print(string.rjust(length, fillchar))
```

**输出:**

```py
***geeks  
```