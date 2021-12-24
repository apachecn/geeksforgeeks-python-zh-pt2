# Python 中的元组()函数

> 原文:[https://www.geeksforgeeks.org/python-tuple-function/](https://www.geeksforgeeks.org/python-tuple-function/)

tuple()函数是 Python 中的内置函数，可用于创建元组。

元组是*不可变的序列类型*。

**语法:**

```py
tuple(iterable)  

```

**参数:**该函数接受单个参数**可迭代(可选)**。这是一个可列表(列表、范围等)..)或迭代器对象。如果传递了一个 iterable，就会创建相应的元组。如果未传递 iterable，将创建空元组。

**返回:**它不返回任何东西，而是创建一个元组。

**错误和异常:**如果未通过可迭代，则返回*类型错误*。

下面的程序说明了 Python 中的 tuple()函数:
**程序 1:** 演示 tuple()函数使用的程序

```py
# Python3 program demonstrating
# the use of tuple() function

# when parameter is not passed
tuple1 = tuple()
print(tuple1)

# when an iterable(e.g., list) is passed
list1= [ 1, 2, 3, 4 ] 
tuple2 = tuple(list1)
print(tuple2)

# when an iterable(e.g., dictionary) is passed
dict = { 1 : 'one', 2 : 'two' } 
tuple3 = tuple(dict)
print(tuple3)

# when an iterable(e.g., string) is passed
string = "geeksforgeeks" 
tuple4 = tuple(string)
print(tuple4)
```

输出:

```py
()
(1, 2, 3, 4)
(1, 2)
('g', 'e', 'e', 'k', 's', 'f', 'o', 'r', 'g', 'e', 'e', 'k', 's')

```

**程序 2:** 演示类型错误的程序

```py
# Python3 program demonstrating 
# the TypeError in tuple() function

# Error when a non-iterable is passed
tuple1 = tuple(1) 
print(tuple1)
```

输出:

```py
Traceback (most recent call last):
  File "/home/eaf759787ade3942e8b9b436d6c60ab3.py", line 5, in 
    tuple1=tuple(1) 
TypeError: 'int' object is not iterable
```