# 在 Python 中快速将十进制转换为其他基数

> 原文:[https://www . geeksforgeeks . org/quick-convert-十进制-base-python/](https://www.geeksforgeeks.org/quickly-convert-decimal-bases-python/)

给定一个十进制数，将其转换为二进制、八进制和十六进制数。下面是将十进制转换为二进制，十进制转换为八进制，十进制转换为十六进制的函数。

示例:

```py
Input : 55
Output : 55  in Binary :  0b110111
         55 in Octal :  0o67
         55  in Hexadecimal :  0x37

Input : 282
Output : 282  in Binary :  0b100011010
         282 in Octal :  0o432
         282  in Hexadecimal :  0x11a

```

一个解决方案是使用下面文章中讨论的方法。

[从任意基数转换为十进制，反之亦然](https://www.geeksforgeeks.org/convert-base-decimal-vice-versa/)

Python 为标准基转换提供了直接函数，如 bin()、hex()和 oct()

```py
# Python program to convert decimal to binary,
# octal and hexadecimal

# Function to convert decimal to binary
def decimal_to_binary(dec):
    decimal = int(dec)

    # Prints equivalent decimal
    print(decimal, " in Binary : ", bin(decimal))

# Function to convert decimal to octal
def decimal_to_octal(dec):
    decimal = int(dec)

    # Prints equivalent decimal
    print(decimal, "in Octal : ", oct(decimal))

# Function to convert decimal to hexadecimal
def decimal_to_hexadecimal(dec):
    decimal = int(dec)

    # Prints equivalent decimal
    print(decimal, " in Hexadecimal : ", hex(decimal))

# Driver program
dec = 32
decimal_to_binary(dec)
decimal_to_octal(dec)
decimal_to_hexadecimal(dec)
```

输出:

```py
32  in Binary :  0b100000
32 in Octal :  0o40
32  in Hexadecimal :  0x20

```

本文由**普拉莫德·库马尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。