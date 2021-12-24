# Python | range()不返回迭代器

> 原文:[https://www . geesforgeks . org/python-range-不返回迭代器/](https://www.geeksforgeeks.org/python-range-does-not-return-an-iterator/)

**range() :** Python range 函数生成一个数字列表，这些数字通常用于许多迭代情况，如 for 循环或许多其他情况。在 python 中，范围对象不是迭代器。range 是不可变对象列表中的一个类。range 的迭代行为类似于 list 中 list 的迭代行为，range 我们不能直接调用 next 函数。如果我们使用 iter 得到一个迭代器，我们可以调用 next。

```
# Python program to understand range
# this creates a list of 0 to 5
# integers

demo = range(6)

# print the demo
print(demo)

# it will generate error
print(next(demo))
```

**输出:**

```
 range(0, 6)

```

**运行时错误:**

```
 Traceback (most recent call last):
  File "/home/6881218331a293819d2a4c16029084f9.py", line 13, in 
    print(next(demo))
TypeError: list object is not an iterator

```

**注意:**以上运行时错误明确表示 python 范围不是迭代器。

因为**范围是可迭代的**，所以我们可以在它们的帮助下得到一个迭代器，但是我们不能直接在 next 中调用 next。下面的例子解释得很清楚

```
# Python program to understand range

# creates an iterator
demo = iter(range(6))

# print iterator
print(demo)

# use next
print(next(demo))
```

**输出:**

```
<listiterator object at 0x7f3f32a46450 >
0

```

当我们创建 range 时，它不会生成它包含的所有数字。它只给出那些我们用循环得到的数字。范围具有以下属性。

*   range 对象是不可变的，这意味着它们不能再次更改，因此可以在字典中用作索引。
*   他们有开始、停止和步进参数。
*   可以一次又一次地访问相同范围

**例**

```
# Python program to understand range

# creates a demo range
demo = range(1, 31, 2)

# print the range
print(demo)

# print the start of range
print(demo.start)

# print step of range
print(demo.step)

# print the index of element 23
print(demo.index(23))

# since 30 is not present it will give error
print(demo.index(30))
```

**输出:**

```
range(1, 31, 2)
1
2
11

```

**运行时错误:**由于元素 30 不存在，它将产生一个错误

```
 Traceback (most recent call last):
  File "/home/cddaae6552d1d9288d7c5ab503c54642.py", line 19, in 
    print(demo.index(30))
ValueError: 30 is not in range

```