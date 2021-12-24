# Python 程序检查两个列表中重叠的前缀-后缀

> 原文:[https://www . geesforgeks . org/python-程序-检查-重叠-前缀-后缀二合一列表/](https://www.geeksforgeeks.org/python-program-to-check-overlapping-prefix-suffix-in-two-lists/)

给定 2 个字符串，我们的任务是检查一个字符串的后缀与另一个字符串的前缀的重叠。

```py
Input : test_str1 = "Gfgisbest", test_str2 = "bestforall"
Output : best

Explanation : best overlaps as suffix of first string and prefix of next.

Input : test_str1 = "Gfgisbest", test_str2 = "restforall"
Output : ''

Explanation : No overlapping.
```

**方法:使用** [**循环**](https://www.geeksforgeeks.org/loops-in-python/) **+** [**切片**](https://www.geeksforgeeks.org/string-slicing-in-python/)**+**[**starts with()**](https://www.geeksforgeeks.org/python-string-startswith/)

在这种情况下，我们增加第一个列表和切片，直到列表结束，并使用 startswith()继续与其他字符串的前缀子字符串进行比较。在这种情况下，出现在字符串末尾的单词与第二个字符串的前缀进行一次比较。

T2T4

```py
# Python3 code to demonstrate working of
# Overlapping Prefix - Suffix in Two Lists
# Using loop + slicing + startswith()
import re

# initializing strings
test_str1 = "Gfgisbest"
test_str2 = "bestforall"

# printing original strings
print("The original string 1 is : " + str(test_str1))
print("The original string 2 is : " + str(test_str2))

res = ''
for char in range(len(test_str1)):

    # using startswith() to get prefix
    if test_str2.startswith(test_str1[char:]):
        res = test_str1[char:]
        break

# printing result
print("Overlapped String  : " + str(res))
```

T5

**输出:**

```py
The original string 1 is : Gfgisbest
The original string 2 is : bestforall
Overlapped String  : best
```