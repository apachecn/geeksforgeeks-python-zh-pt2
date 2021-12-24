# Python 字符串方法|集合 1 (find，rfind，startwith，endwith，islower，isupper，lower，upper，swapcase & title)

> 原文:[https://www . geesforgeks . org/python-string-methods-set-1-find-rfind-startwith-endwith-is lower-is upper-lower-upper-swap case-title/](https://www.geeksforgeeks.org/python-string-methods-set-1-find-rfind-startwith-endwith-islower-isupper-lower-upper-swapcase-title/)

一些弦乐基础知识已经在下面的文章
[弦乐第 1 部分](https://www.geeksforgeeks.org/interesting-facts-about-strings-in-python-set-1/)
[弦乐第 2 部分](https://www.geeksforgeeks.org/interesting-facts-about-strings-in-python-set-2/)
中介绍过，重要的弦乐方法将在本文
**1 中讨论。find(“string”，beg，end)** :-该函数用于查找子串在字符串中的位置。它采用 3 个参数，**子串，起始索引(默认为 0)和结束索引(默认为字符串长度)**。

*   如果在给定范围内未找到字符串，则返回“-1”。
*   如果找到，它将返回字符串的第一个匹配项。

**2。rfind("string "，beg，end)** :-此函数的工作方式与 find()类似，但它返回字符串最后一次出现的**的位置。** 

## **计算机编程语言**

```py
# Python code to demonstrate working of
# find() and rfind()
str = "geeksforgeeks is for geeks"
str2 = "geeks"

# using find() to find first occurrence of str2
# returns 8
print ("The first occurrence of str2 is at : ", end="")
print (str.find( str2, 4) )

# using rfind() to find last occurrence of str2
# returns 21
print ("The last occurrence of str2 is at : ", end="")
print ( str.rfind( str2, 4) )
```

**输出:** 

```py
The first occurrence of str2 is at : 8
The last occurrence of str2 is at : 21
```

****3。startswith("string "，beg，end)** :-如果函数**以提到的字符串(前缀)**开头，则该函数返回 true，否则返回 false。
**4。endswith("string "，beg，end)** :-如果**函数以提到的 string(后缀)**结尾，则该函数的目的是返回 true，否则返回 false。** 

## **蟒蛇 3**

```py
# Python code to demonstrate working of
# startswith() and endswith()
str = "geeks"
str1 = "geeksforgeeksportal"

# using startswith() to find if str
# starts with str1
if str1.startswith(str):
        print ("str1 begins with : " + str)
else : print ("str1 does not begin with : "+ str)

# using endswith() to find
# if str ends with str1
if str1.endswith(str):
    print ("str1 ends with : " + str)
else :
    print ("str1 does not end with : " + str)
```

**输出:** 

```py
str1 begins with : geeks
str1 does not end with : geeks
```

****5。islower(“字符串”)** :-如果字符串中的所有字母都是**小写，**则该函数返回 true，否则返回 false。
**6。isupper(“字符串”)** :-如果字符串中的所有字母都是**大写**，则该函数返回 true，否则返回 false。** 

## **蟒蛇 3**

```py
# Python code to demonstrate working of
# isupper() and islower()
str = "GeeksforGeeks"
str1 = "geeks"

# checking if all characters in str are upper cased
if str.isupper() :
    print ("All characters in str are upper cased")
else :
    print ("All characters in str are not upper cased")

# checking if all characters in str1 are lower cased
if str1.islower() :
    print ("All characters in str1 are lower cased")
else :
    print ("All characters in str1 are not lower cased")
```

**输出:** 

```py
All characters in str are not upper cased
All characters in str1 are lower cased
```

****7。lower()** :-该函数返回新字符串，所有字母**都转换为小写**。
**8。upper()** :-该函数返回新字符串，所有字母**转换为大写**。
**9。swapcase()** :-该函数用于交换字符串的大小写，即大写转换为小写，反之亦然。
**10。title()** :-该函数将字符串转换为其**标题大小写**，即字符串每个单词的第一个字母都是大写的，否则都是小写的。** 

## **蟒蛇 3**

```py
# Python code to demonstrate working of
# upper(), lower(), swapcase() and title()
str = "GeeksForGeeks is fOr GeeKs"

# Converting string into its lower case
str1 = str.lower();
print (" The lower case converted string is : " + str1)

# Converting string into its upper case
str2 = str.upper();
print (" The upper case converted string is : " + str2)

# Converting string into its swapped case
str3 = str.swapcase();
print (" The swap case converted string is : " + str3)

# Converting string into its title case
str4 = str.title();
print (" The title case converted string is : " + str4)
```

**输出:** 

```py
 The lower case converted string is : geeksforgeeks is for geeks
 The upper case converted string is : GEEKSFORGEEKS IS FOR GEEKS
 The swap case converted string is : gEEKSfORgEEKS IS FoR gEEkS
 The title case converted string is : Geeksforgeeks Is For Geeks
```

**本文由**曼吉特·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**