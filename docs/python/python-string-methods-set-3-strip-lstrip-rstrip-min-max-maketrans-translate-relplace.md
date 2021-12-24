# Python 字符串方法|集合 3 (strip，lstrip，rstrip，min，max，maketrans，trans，translate，replace & expandtabs())

> 原文:[https://www . geesforgeks . org/python-string-methods-set-3-strip-lstrip-rstrip-min-max-make trans-translate-relplace/](https://www.geeksforgeeks.org/python-string-methods-set-3-strip-lstrip-rstrip-min-max-maketrans-translate-relplace/)

一些字符串方法包含在下面的集合中。
[弦法 Part- 1](https://www.geeksforgeeks.org/python-string-methods-set-1-find-rfind-startwith-endwith-islower-isupper-lower-upper-swapcase-title/)
[弦法 Part- 2](https://www.geeksforgeeks.org/python-string-methods-set-2-len-count-center-ljust-rjust-isalpha-isalnum-isspace-join/)
更多方法在本文
**1 中讨论。strip()** :-此方法用于**删除其参数中提到的所有前导和尾随**字符。
**2。lstrip()** :-此方法用于**删除其参数中提到的所有前导**字符。
**3。rstrip()** :-此方法用于**删除其参数中提到的所有尾随**字符。

## 计算机编程语言

```
# Python code to demonstrate working of
# strip(), lstrip() and rstrip()
str = "---geeksforgeeks---"

# using strip() to delete all '-'
print ( " String after stripping all '-' is : ", end="")
print ( str.strip('-') )

# using lstrip() to delete all trailing '-'
print ( " String after stripping all leading '-' is : ", end="")
print ( str.lstrip('-') )

# using rstrip() to delete all leading '-'
print ( " String after stripping all trailing '-' is : ", end="")
print ( str.rstrip('-') )
```

输出:

```
 String after stripping all '-' is : geeksforgeeks
 String after stripping all leading '-' is : geeksforgeeks---
 String after stripping all trailing '-' is : ---geeksforgeeks
```

**4。min(“字符串”)** :-该函数从字符串中返回**最小值字母表**。
**5。max(“字符串”)** :-该函数从字符串返回**最大值字母表**。

## 计算机编程语言

```
# Python code to demonstrate working of
# min() and max()
str = "geeksforgeeks"

# using min() to print the smallest character
# prints 'e'
print ("The minimum value character is : " + min(str))

# using max() to print the largest character
# prints 's'
print ("The maximum value character is : " + max(str))
```

输出:

```
The minimum value character is : e
The maximum value character is : s
```

**6。maketrans()** :-它用于将字符串 1 的内容与字符串 2 的内容进行映射，并使用 translate()对其索引进行翻译。
**7。translate()** :-这是用来在 maketrans()的帮助下**交换映射的字符串元素**。

## 计算机编程语言

```
# Python code to demonstrate working of
# maketrans() and translate()
from string import maketrans # for maketrans()

str = "geeksforgeeks"

str1 = "gfo"
str2 = "abc"

# using maktrans() to map elements of str2 with str1
mapped = maketrans( str1, str2 )

# using translate() to translate using the mapping
print "The string after translation using mapped elements is : "
print  str.translate(mapped)
```

输出:

```
The string after translation using mapped elements is : 
aeeksbcraeeks
```

在上面的代码中，在使用 translate 函数的字符串中，“g”被 a 替换，“f”被 b 替换，“o”被“c”替换。
**8.replace()** :-该函数用于**将字符串中的子字符串替换为新的子字符串**。这个函数有 3 个参数。**要替换的字符串、要替换的新字符串以及表示替换操作限制的最大值(默认情况下无限制)。**

## 计算机编程语言

```
# Python code to demonstrate working of
# replace()

str = "nerdsfornerds is for nerds"

str1 = "nerds"
str2 = "geeks"

# using replace() to replace str2 with str1 in str
# only changes 2 occurrences
print ("The string after replacing strings is : ", end="")
print (str.replace( str1, str2, 2))
```

输出:

```
The string after replacing strings is : geeksforgeeks is for nerds
```

这个方法是由[钦莫伊蕾恩卡](https://auth.geeksforgeeks.org/user/Chinmoy%20Lenka)T2**9 贡献的。expandtabs()** :-用于**将所有制表符(" \t ")替换为空格**或使用给定的制表符大小简单地替换空格，可选提供。
语法:string.tabsize(tabsize)
参数:指定一个 tab 字符要替换的字符数。默认情况下，该函数采用标签大小为 8。
返回值:所有制表符都被空格替换的字符串。

## 蟒蛇 3

```
# Python code to illustrate expandtabs()
string = 'GEEKS\tFOR\tGEEKS'

# No parameters, by default size is 8
print (string.expandtabs())

# tab size taken as 2
print(string.expandtabs(2))

# tab size taken as 5
print(string.expandtabs(5))
```

输出:

```
GEEKS   FOR     GEEKS
GEEKS FOR GEEKS
GEEKS     FOR  GEEKS
```

本文由 [**【曼吉特·辛格】**](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。