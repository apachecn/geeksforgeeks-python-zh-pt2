# Python 中的 turtle.isvisible()函数

> 原文:[https://www . geesforgeks . org/turtle-is visible-function-in-python/](https://www.geeksforgeeks.org/turtle-isvisible-function-in-python/)

海龟模块以面向对象和面向过程的方式提供海龟图形原语。因为它使用 Tkinter 作为底层图形，所以它需要安装一个支持 Tk 的 Python 版本。

## turtle.isvisible()

方法的作用是:如果显示了海龟，返回真；如果隐藏了海龟，返回假。这个方法不需要任何参数。

**语法:**

```
turtle.isvisible()

```

为了更好的理解，下面是上述方法的实现:

**例 1:**

## 蟒蛇 3

```
# import package
import turtle

# check turtle visibility
print(turtle.isvisible())

# motion
turtle.forward(100)
turtle.right(90)

# hide the turtle
turtle.ht()

# motion
turtle.forward(100)

# check turtle visibility
print(turtle.isvisible())

# motion
turtle.right(90)
turtle.forward(100)

# show the turtle
turtle.st()

# check turtle visibility
print(turtle.isvisible())
```

**输出:**

![](img/d7dc3940cb9a496b3f2fa84ad0229cd4.png)

```
True
False
True

```