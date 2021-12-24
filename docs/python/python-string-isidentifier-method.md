# Python 字符串标识符()方法

> 原文:[https://www . geeksforgeeks . org/python-string-isiidentifier-method/](https://www.geeksforgeeks.org/python-string-isidentifier-method/)

python String**is identifier()**方法用于检查字符串是否是有效的标识符。如果字符串是有效的标识符，则方法返回真，否则返回假。

> **语法:**
> 
> string . isidentifier()
> 
> **参数:**
> 
> 该方法不采用任何参数
> 
> **返回值:**
> 
> 该方法可以返回两个值之一:
> 
> *   **真:**当字符串是有效标识符时。
> *   **False:** 当字符串不是有效的标识符时。

### 示例:isidentifier()如何工作

## 蟒蛇 3

```py
# Python code to illustrate 
# the working of isidentifier()

# String with spaces
string = "Geeks for Geeks"
print(string.isidentifier())

# A Perfect identifier
string = "GeeksforGeeks"
print(string.isidentifier())

# Empty string
string = ""
print(string.isidentifier())

# Alphanumerical string
string = "Geeks0for0Geeks"
print(string.isidentifier())

# Beginning with an integer
string = "54Geeks0for0Geeks"
print(string.isidentifier())
```

**输出:**

```py
False
True
False
True
False
```