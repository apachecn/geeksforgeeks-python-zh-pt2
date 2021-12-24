# Python 字符串方法|集合 2 (len，count，center，ljust，rjust，isalpha，isalnum，isspace & join)

> 原文:[https://www . geesforgeks . org/python-string-methods-set-2-len-count-center-ljust-rjust-isalpha-isalnum-isspace-join/](https://www.geeksforgeeks.org/python-string-methods-set-2-len-count-center-ljust-rjust-isalpha-isalnum-isspace-join/)

一些弦乐方法包含在下面的第 3 集
[弦乐方法第 1 部分](https://www.geeksforgeeks.org/python-string-methods-set-1-find-rfind-startwith-endwith-islower-isupper-lower-upper-swapcase-title/)

本文将讨论更多方法

**1。len()** :-该函数返回字符串的**长度**。

**2。count(“string”，beg，end)** :-此功能**统计整个字符串中所提到的**子串**的出现次数**。该函数采用 3 个参数，s**substring，起始位置(默认为 0)和结束位置(默认为字符串长度)。**

```py
# Python code to demonstrate working of 
# len() and count()
str = "geeksforgeeks is for geeks"

# Printing length of string using len()
print (" The length of string is : ", len(str));

# Printing occurrence of "geeks" in string
# Prints 2 as it only checks till 15th element
print (" Number of appearance of ""geeks"" is : ",end="")
print (str.count("geeks",0,15))
```

输出:

```py
 The length of string is :  26
 Number of appearance of geeks is : 2

```

**3。center()** :-该功能用于用一个字符多次重复字符串两边来包围字符串**。默认情况下，字符是空格。采用 2 个参数，**长度的字符串和字符。****

**4。ljust()** :-该函数返回向左移动的**原始字符串**，该字符串的右侧有一个**字符**。它向左调整弦。默认情况下，字符是空格。它还需要两个参数，**字符串长度和字符。** 
**5。rjust()** :-该函数返回向右移动的**原始字符串**，其左侧有一个**字符**。它能调整琴弦。默认情况下，字符是空格。它还需要两个参数，**字符串长度和字符。**

```py
# Python code to demonstrate working of 
# center(), ljust() and rjust()
str = "geeksforgeeks"

# Printing the string after centering with '-'
print ("The string after centering with '-' is : ",end="")
print ( str.center(20,'-'))

# Printing the string after ljust()
print ("The string after ljust is : ",end="")
print ( str.ljust(20,'-'))

# Printing the string after rjust()
print ("The string after rjust is : ",end="")
print ( str.rjust(20,'-'))
```

输出:

```py
The string after centering with '-' is : ---geeksforgeeks----
The string after ljust is : geeksforgeeks-------
The string after rjust is : -------geeksforgeeks

```

**6。isalpha()** :-当字符串中的所有字符都是**字母**时，该函数返回真，否则返回假。

**7。isalnum()** :-当字符串中的所有字符都是数字和/或字母的组合**时，该函数返回真，否则返回假。**

**8。isspace()** :-当字符串中所有字符都是**空格**时，此函数返回真，否则返回假。

```py
# Python code to demonstrate working of 
# isalpha(), isalnum(), isspace()
str = "geeksforgeeks"
str1 = "123"

# Checking if str has all alphabets 
if (str.isalpha()):
       print ("All characters are alphabets in str")
else : print ("All characters are not alphabets in str")

# Checking if str1 has all numbers
if (str1.isalnum()):
       print ("All characters are numbers in str1")
else : print ("All characters are not numbers in str1")

# Checking if str1 has all spaces
if (str1.isspace()):
       print ("All characters are spaces in str1")
else : print ("All characters are not spaces in str1")
```

输出:

```py
All characters are alphabets in str
All characters are numbers in str1
All characters are not spaces in str1

```

**9。join()** :-该函数用于将参数中提到的字符串序列与字符串连接起来**。**

```py
# Python code to demonstrate working of 
# join()
str = "_"
str1 = ( "geeks", "for", "geeks" )

# using join() to join sequence str1 with str
print ("The string after joining is : ", end="")
print ( str.join(str1))
```

输出:

```py
The string after joining is : geeks_for_geeks

```

本文由**曼吉特·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。