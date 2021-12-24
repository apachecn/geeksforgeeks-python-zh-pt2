# Python 程序打印 hello world

> 原文:[https://www . geesforgeks . org/python-程序转打印-hello-world/](https://www.geeksforgeeks.org/python-program-to-print-hello-world/)

**先决条件:** [Python 语言介绍](https://www.geeksforgeeks.org/python-language-introduction/)、 [Python 3 基础知识](https://www.geeksforgeeks.org/python-3-basics/)

在本文中，我们将研究如何用 Python 打印“Hello World”。

## **方法 1:使用 Print()**

在这里，我们将使用 python print()函数进行同样的操作。python 中的 print()函数用于将 python 对象作为字符串打印为标准输出。

**python 打印功能有以下语法:**

> **语法:**打印(“字符串”)
> 
> **其中:字符串:**这个字符串会是【Hello world】

**实现:**

## 蟒 3

```py
# python program to print "Hello World"
print("Hello World")
```

**输出:**

```py
Hello World
```

## 方法二:使用[系统](https://www.geeksforgeeks.org/python-sys-module/)

在此方法中，我们将使用 sys 模块打印字符串，Python 中的 **sys 模块** 提供了各种函数和变量，用于操作 Python 运行时环境的不同部分。它允许在解释器上操作，因为它提供了对与解释器强交互的变量和函数的访问。

[**sys . STD . write():**](https://www.geeksforgeeks.org/sys-stdout-write-in-python/)stdout 用于直接向屏幕控制台显示输出。

> **语法:**sys . stdout . write(" String ")

**代号:**

## 蟒 3

```py
import sys

sys.stdout.write("Hello World")
```

**输出:**

```py
Hello World
```