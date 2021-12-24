# python()中的 String rjust()和 ljust()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/string-rust-ljust-python/

**1。string rjust()**string**rjust()**方法在原始字符串左侧替换给定字符后，返回给定长度的新字符串。

**语法:**

> string.rjust(长度，fillchar)

**参数:**

> **长度:**修改后字符串的长度。如果长度小于或等于原始字符串的长度，则返回原始字符串。
> **fillchar:** (可选)需要填充的字符。如果没有提供，空间将作为默认参数。

**返回:**

> 在原始字符串左侧替换给定字符后，返回给定长度的新字符串。

**例**

```
# Python program to demonstrate working of 
# rjust()
string = 'geeks'
length = 8

# If no fill character is provided, space
# is used as fill character
print(string.rjust(length))
```

输出:

```
   geeks
```

**例**

```
# example string
string = 'geeks'
length = 8
fillchar = '*'

print(string.rjust(length, fillchar))
```

输出:

```
***geeks  

```

**2。字符串 ljust()**
字符串 **ljust()** 方法在原始字符串右侧替换给定字符后，返回给定长度的新字符串。

**语法:**

> string.ljust(长度、文件长度)

**参数:**

> **长度:**修改后字符串的长度。如果长度小于或等于原始字符串的长度，则返回原始字符串。
> **fillchar:** (可选)需要填充的字符。如果没有提供，空间将作为默认参数。

**返回:**

> 在原始字符串右侧替换给定字符后，返回给定长度的新字符串。

**例 1**

```
# example string
string = 'geeks'
length = 8

# If no fill character is provided, space
# is used as fill character.
print(string.ljust(length))
```

输出:(极客后打印三个空格)

```
geeks   

```

**例 2**

```
# example string
string = 'geeks'
length = 8
fillchar = '*'

# print left justified string
print(string.ljust(length, fillchar))
```

输出:

```
geeks***  

```