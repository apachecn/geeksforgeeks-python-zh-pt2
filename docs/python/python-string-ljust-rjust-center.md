# Python 字符串\ ljust()、rj()、center()

> 原文:[https://www . geesforgeks . org/python-string-ljust-rjust-center/](https://www.geeksforgeeks.org/python-string-ljust-rjust-center/)

字符串对齐在许多日常应用中经常使用。Python 在其语言中提供了几个有助于对齐字符串的函数。此外，还提供了一种添加用户指定的填充而不是空白的方法。

这些功能是:

```py
str.ljust(s, width[, fillchar])
str.rjust(s, width[, fillchar])
str.center(s, width[, fillchar])

```

这些函数分别在给定宽度的字段中左对齐、右对齐和居中。它们返回一个宽度至少为字符宽的字符串，该字符串是通过用字符*填充字符串*直到右侧、左侧或两侧的给定宽度而创建的。字符串永远不会被截断。

**center()**

此函数 ***根据指定的宽度居中对齐*** 字符串，如果未传递“ *fillchr* ”参数，则用空格填充行的剩余空间。

> **语法:**
> 中心(len，fillchr)
> 
> **参数:**
> **len :** 把弦的宽度扩大一下。
> **填充符(可选):**要填充剩余空间的字符。
> 
> **返回值:**
> 合成的中心对齐字符串扩展了给定的宽度。

```py
# Python3 code to demonstrate 
# the working of center()

cstr = "I love geeksforgeeks"

# Printing the original string
print ("The original string is : \n", cstr, "\n")

# Printing the center aligned string 
print ("The center aligned string is : ")
print (cstr.center(40), "\n")

# Printing the center aligned 
# string with fillchr
print ("Center aligned string with fillchr: ")
print (cstr.center(40, '#'))
```

输出:

```py
The original string is : 
 I love geeksforgeeks 

The center aligned string is : 
          I love geeksforgeeks           

Center aligned string with fillchr: 
##########I love geeksforgeeks##########

```

**ljust()**

此函数 ***根据指定的宽度左对齐*** 字符串，如果未传递“ *fillchr* ”参数，则用空格填充行的剩余空间。

> **语法**T2】灯(len，fillchr)
> 
> **参数:**
> **len :** 把弦的宽度扩大一下。
> **填充符(可选):**要填充剩余空间的字符。
> 
> **返回值:**
> 结果左对齐字符串扩展给定宽度。

```py
# Python3 code to demonstrate 
# the working of  ljust()

lstr = "I love geeksforgeeks"

# Printing the original string
print ("The original string is : \n", lstr, "\n")

# Printing the left aligned 
# string with "-" padding 
print ("The left aligned string is : ")
print (lstr.ljust(40, '-'))
```

输出:

```py
The original string is : 
 I love geeksforgeeks 

The left aligned string is : 
I love geeksforgeeks--------------------
```

**rjust()**

如果未传递“ *fillchr* ”参数，该函数**根据指定的宽度将字符串右对齐**，并用空格填充行的剩余空间。

> **语法:**
> rjust( len，fillchr)
> 
> **参数:**
> **len :** 把弦的宽度扩大一下。
> **填充符(可选):**要填充剩余空间的字符。
> 
> **返回值:**
> 结果右对齐字符串扩展给定宽度。

```py
# Python3 code to demonstrate 
# the working of rjust()

rstr = "I love geeksforgeeks"

# Printing the original string
print ("The original string is : \n", rstr, "\n")

# Printing the right aligned string
# with "-" padding 
print ("The right aligned string is : ")
print (rstr.rjust(40, '-'))
```

输出:

```py
The original string is : 
 I love geeksforgeeks 

The right aligned string is : 
--------------------I love geeksforgeeks
```