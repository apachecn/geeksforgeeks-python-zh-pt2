# Python 中的 turtle.resizemode()函数

> 原文:[https://www . geesforgeks . org/turtle-resize mode-python 中的函数/](https://www.geeksforgeeks.org/turtle-resizemode-function-in-python/)

海龟模块以面向对象和面向过程的方式提供海龟图形原语。因为它使用 Tkinter 作为底层图形，所以它需要安装一个支持 Tk 的 Python 版本。

## turtle.resizemode()

该函数用于将 resizemode 设置为以下值之一:“auto”、“user”、“noresize”。如果没有给定参数，返回当前的 resizemode。resizemode("user ")是通过调用 shapesize 参数来调用的。

> **语法:**turtle . resize mode(rmode = None)
> 
> **参数:**
> 
> **rmode(可选):**字符串“自动”、“用户”、“noresize”之一
> 
> 不同的调整大小模式具有以下效果:
> 
> *   “自动”使海龟的外观与 pensize 的值相对应。
> *   “用户”根据由 shapesize()设置的 stretchfactor 和 outlinewidth(轮廓)的值来调整海龟的外观
> *   没有发生海龟外貌的变化。

下面是上述方法的实现，并附有一些例子:

**例 1 :**

## 蟒蛇 3

```py
# importing package
import turtle

# check default value
print(turtle.resizemode())
```

**输出:**

```py
noresize

```

**例 2 :**

## 蟒蛇 3

```py
# importing package
import turtle

# print default value
print(turtle.resizemode())

# change mode to auto and check
turtle.resizemode(rmode="auto")
print(turtle.resizemode())

# change mode to user and check
turtle.resizemode(rmode="user")
print(turtle.resizemode())
```

**输出:**

```py
noresize
auto
user

```