# Python 字符串 maketrans()方法

> 原文:[https://www . geesforgeks . org/python-string-make trans-method/](https://www.geeksforgeeks.org/python-string-maketrans-method/)

Python String maketrans()函数用于构造转换表，即指定需要在整个字符串中替换的字符列表或需要从字符串中删除的字符。

> **语法:**
> 
> maktrans(str 1、str2、str3)
> 
> **参数:**
> 
> *   **str1** :指定需要替换的字符列表。
> *   **str2** :指定需要替换字符的字符列表。
> *   **str3** :指定需要删除的字符列表。
> 
> **返回:**
> 
> 返回指定 translate()可以使用的转换的转换表

### 使用 maketrans()翻译

翻译字符串中的字符 translate()用于进行翻译。此函数使用使用 maketrans()指定的转换映射。

> ***语法:***
> 
> 平移(表，del tr)
> 
> ***参数:***
> 
> *   ***表:**翻译映射指定执行翻译。*
> *   ***delstr:** 删除字符串可以指定为可选参数，表中没有提到。*
> 
> ***返回:**使用翻译表执行翻译后返回参数字符串。*

### 示例:使用 translate()和 maketrans()进行翻译的代码

## 蟒蛇 3

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

**输出:**

```py
The string before translating is : weeksyourweeks
The string after translating is : geeksforgeeks
```