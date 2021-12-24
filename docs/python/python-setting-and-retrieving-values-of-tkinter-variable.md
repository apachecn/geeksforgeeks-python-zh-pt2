# Python |设置和检索 Tkinter 变量的值

> 原文:[https://www . geesforgeks . org/python-设置和检索-tkinter-variable 的值/](https://www.geeksforgeeks.org/python-setting-and-retrieving-values-of-tkinter-variable/)

Tkinter 支持一些用于操作 Tkinter 小部件值的变量。这些变量就像普通变量一样工作。
set()和 get()方法用于设置和检索这些变量的值。
这些变量的值可以用 set()方法设置，也可以用这些变量的构造函数设置。
共有 4 个变量。

*   BooleanVar()
*   StringVar()
*   IntVar（）
*   DoubleVar()

## 设置 Tkinter 变量的值–

**1。使用变量的构造函数**
**语法:**

```py
var = Tkinter_variable(master, value = any_value)
```

## 蟒蛇 3

```py
# importing tkinter module
from tkinter import *

# creating Tk() variable
# required by Tkinter classes
master = Tk()

# Tkinter variables
# initialization using constructor
intvar = IntVar(master, value = 25, name ="2")
strvar = StringVar(master, "Hello !")
boolvar = BooleanVar(master, True)
doublevar = DoubleVar(master, 10.25)
```