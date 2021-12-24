# 去除所有控制字符的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序移除所有控制字符/](https://www.geeksforgeeks.org/python-program-to-remove-all-control-characters/)

在电信和计算机领域，控制字符是不可打印的字符，是字符集的一部分。这些不代表任何书面符号。除了给文本添加符号之外，它们还用于发出信号以产生某些效果。移除这些控制字符是一个必不可少的工具。在本文中，我们将讨论如何删除所有这些控制字符。

**示例:**

> **输入:**test _ str = ' Geeks \ 0 \ r for \ n \ Bge \ tee \ 0ks \ f '
> 
> **输出:**geek 的极客
> 
> **解释:** \n，\0，\f，\r，\b，t 是从字符串中删除的控制字符。
> 
> **输入:** test_str = 'G\0\r\n\fg '
> 
> **输出:** Gfg
> 
> **解释:** \n，\0，\f，\r 是从字符串中删除的控制字符，给出 Gfg 作为输出。

**方法一:使用** [**翻译()。**](https://www.geeksforgeeks.org/python-string-translate/#:~:text=translate()%20returns%20a%20string,according%20to%20given%20translation%20mappings.&text=mapping%20%E2%80%93%20a%20dictionary%20having%20mapping,to%20the%20provided%20mapping%20table.)

这里应用的逻辑是，每个非控制字符位于前 33 个 ASCII 字符处，因此通过映射，使用翻译来避免除这些字符之外的所有其他字符。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Remove all control characters
# Using translate()

# initializing string
test_str = 'Geeks\0\r for \n\bge\tee\0ks\f'

# printing original string
print("The original string is : " + str(test_str))

# using translate() and fromkeys()
# to escape all control characters
mapping =  dict.fromkeys(range(32))
res = test_str.translate(mapping)

# printing result
print("String after removal of control characters : " + str(res))
```

**输出:**

```
 for riginal string is : Geeks
ge    eeks
String after removal of control characters : Geeks for geeeks
```

**方法二:使用** [**unicodedata 库**](https://www.geeksforgeeks.org/unicodedata-unicode-database-python/#:~:text=unicodedata.bidirectional(chr),no%20such%20value%20is%20defined.)

在这种情况下，使用 unicodedata.category()，我们可以检查以“C”开头的每个字符是否是控制字符，从而避免在结果字符串中出现。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Remove all control characters
# Using unicodedata library
import unicodedata

# initializing string
test_str = 'Geeks\0\r for \n\bge\tee\0ks\f'

# printing original string
print("The original string is : " + str(test_str))

# surpassing all control characters
# checking for starting with C
res = "".join(char for char in test_str if unicodedata.category(char)[0]!="C")

# printing result
print("String after removal of control characters : " + str(res))
```

**输出:**

```
 for riginal string is : Geeks
ge    eeks
String after removal of control characters : Geeks for geeeks
```