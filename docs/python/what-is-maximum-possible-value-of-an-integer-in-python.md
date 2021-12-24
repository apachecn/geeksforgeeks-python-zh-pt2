# Python 中整数的最大可能值是多少？

> 原文:[https://www . geesforgeks . org/什么是 python 中整数的最大可能值/](https://www.geeksforgeeks.org/what-is-maximum-possible-value-of-an-integer-in-python/)

考虑下面的 Python 程序。

## 计算机编程语言

```
# A Python program to demonstrate that we can store
# large numbers in Python

x = 10000000000000000000000000000000000000000000
x = x + 1
print (x)
```

输出:

```
10000000000000000000000000000000000000000001
```

***在 Python 中，一个整数的值不受位数的限制，可以扩展到可用内存的极限(来源:*** [***本***](https://docs.python.org/2/library/stdtypes.html) ***和*** [***本***](http://www.cs.utexas.edu/users/mitra/csSpring2016/cs313/lectures/math.html)***)***。因此，我们从来不需要任何特殊的排列来存储大数(想象一下用 C/C++做上面的算术)。
顺便提一下，在 Python 3 中，所有类型的整数只有一种类型“int”。在 Python 2.7 中。有两种单独的类型“int”(32 位)和与 Python 3.x 的“int”相同的“long int”，即可以存储任意大的数字。

## 计算机编程语言

```
# A Python program to show that there are two types in
# Python 2.7 : int and long int
# And in Python 3 there is only one type : int

x = 10
print(type(x))

x = 10000000000000000000000000000000000000000000
print(type(x))
```

**Python 2.7 中的输出:**

```
<type 'int'>
<type 'long'>
```

**Python 3 中的输出:**

```
<type 'int'>
<type 'int'>
```

我们可能想尝试更多有趣的程序，如下所示:

## 计算机编程语言

```
# Printing 100 raise to power 100
print(100**100)
```

本文由**阿沛·拉提**供稿。如果你发现任何不正确的地方，请写评论，或者你想分享更多关于上面讨论的话题的信息