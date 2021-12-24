# Python 中 maketrans()和 translate()函数

> 原文:[https://www . geesforgeks . org/python-make trans-translate-functions/](https://www.geeksforgeeks.org/python-maketrans-translate-functions/)

在编程领域，很少需要一次替换整个文件中的所有单词/字符。python 使用函数 translate()及其助手函数 maketrans()提供了这一功能。本文将讨论这两种功能。

**maketrans()**

maketrans()函数用于构造转换表，即指定需要在整个字符串中替换的字符列表或需要从字符串中删除的字符列表

> 语法: **maketrans(str1，str2，str3)**
> 
> **参数:**
> **str1 :** 指定需要替换的字符列表。
> **str2 :** 指定需要替换字符的字符列表。
> **str3 :** 指定需要删除的字符列表。
> 
> **返回:**返回指定 translate()可以使用的转换的转换表

**Translate using maketrans()**

翻译字符串中的字符 translate()用于进行翻译。此函数使用使用 maketrans()指定的转换映射。

> 语法:平移(表，del tr)
> 
> **参数:**
> **表:**翻译映射指定执行翻译。
> **delstr :** 删除字符串可以指定为可选参数，表中没有提到。
> 
> **返回:**使用翻译表执行翻译后返回参数字符串。

**代码#1 :** 使用 translate()和 maketrans()进行翻译的代码。

```py
# Python3 code to demonstrate 
# translations using 
# maketrans() and translate()

# specify to translate chars
str1 = "wy"

# specify to replace with
str2 = "gf"

# delete chars
str3 = "u"

# target string 
trg = "weeksyourweeks"

# using maketrans() to 
# construct translate
# table
table = trg.maketrans(str1, str2, str3)

# Printing original string 
print ("The string before translating is : ", end ="")
print (trg)

# using translate() to make translations.
print ("The string after translating is : ", end ="")
print (trg.translate(table))
```

输出:

```py
The string before translating is : weeksyourweeks
The string after translating is : geeksforgeeks

```

**Translate without maketrans()**

翻译也可以通过指定翻译字典和作为映射的对象传递来实现。在这种情况下，maketrans()不需要执行翻译。

**代码#2 :** 无需 maketrans()即可翻译的代码。

```py
# Python3 code to demonstrate 
# translations without
# maketrans() 

# specifying the mapping 
# using ASCII 
table = { 119 : 103, 121 : 102, 117 : None }

# target string 
trg = "weeksyourweeks"

# Printing original string 
print ("The string before translating is : ", end ="")
print (trg)

# using translate() to make translations.
print ("The string after translating is : ", end ="")
print (trg.translate(table))
```

输出:

```py
The string before translating is : weeksyourweeks
The string after translating is : geeksforgeeks

```

**应用:**
在编码或开发过程中，有很多时候会出现错误，这些功能提供了一种简单快捷的方法来替换和纠正它们，并可能节省大量时间。