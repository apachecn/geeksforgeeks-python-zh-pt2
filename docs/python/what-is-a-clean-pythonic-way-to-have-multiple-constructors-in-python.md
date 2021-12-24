# 在 Python 中拥有多个构造函数，什么是干净、Python 化的方式？

> 原文:[https://www . geeksforgeeks . org/什么是干净的 python 中有多个构造函数的方法/](https://www.geeksforgeeks.org/what-is-a-clean-pythonic-way-to-have-multiple-constructors-in-python/)

**先决条件–**[**构造器**](https://www.geeksforgeeks.org/constructors-in-python/) **、** [**@classmethod 装饰器**](https://www.geeksforgeeks.org/classmethod-in-python/)

Python 不支持显式的多个构造函数，但是有一些方法可以实现多个构造函数。如果为同一个类编写了多个 [**__init__**](https://www.geeksforgeeks.org/__init__-in-python/) 方法，那么最新的方法会覆盖所有以前的构造函数。请看下面的例子。

## python 3

```py
class example:

    def __init__(self):
        print("One")

    def __init__(self):
        print("Two")

    def __init__(self):
        print("Three")

e = example()
```

**输出**

```py
Three

```