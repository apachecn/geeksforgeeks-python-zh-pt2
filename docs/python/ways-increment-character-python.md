# 在 Python 中增加字符的方法

> 原文:[https://www . geesforgeks . org/way-increment-character-python/](https://www.geeksforgeeks.org/ways-increment-character-python/)

在 python 中，没有数据类型的隐式概念，尽管数据类型的显式转换是可能的，但是对于我们来说，指导操作符以某种方式工作并理解操作数的数据类型并据此进行操作并不容易。例如**给一个字符加 1，如果我们要求增加字符，就会出现一个错误指令类型冲突**，因此需要制定其他方式来增加字符。

## 计算机编程语言

```
# python code to demonstrate error
# due to incrementing a character

# initializing a character
s = 'M'

# trying to get 'N'
# produces error
s = s + 1

print (s)
```

输出:

```
Traceback (most recent call last):
  File "/home/fabc221bf999b96195c763bf3c03ddca.py", line 9, in 
    s = s + 1
TypeError: cannot concatenate 'str' and 'int' objects
```

**Using ord() + chr()**

## 蟒蛇 3

```
# python code to demonstrate way to
# increment character

# initializing character
ch = 'M'

# Using chr()+ord()
# prints P
x = chr(ord(ch) + 3)

print ("The incremented character value is : ",end="")
print (x)
```

输出:

```
The incremented character value is : P
```

**说明:**order()返回字符对应的 ASCII 值，加上整数后，chr()再次转换为字符。

**Using byte string**

## 蟒蛇 3

```
# python code to demonstrate way to
# increment character

# initializing byte character
ch = 'M'

# converting character to byte
ch = bytes(ch, 'utf-8')

# adding 10 to M
s = bytes([ch[0] + 10])

# converting byte to string
s = str(s)

# printing the required value
print ("The value of M after incrementing 10 places is : ",end="")
print (s[2])
```

输出:

```
The value of M after incrementing 10 places is : W
```

**说明:**字符被转换为字节字符串，递增，然后再次转换为前缀为“‘b’的字符串形式，因此第三个值给出了正确的输出。
本文由[](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04)**曼吉特·辛格供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。**