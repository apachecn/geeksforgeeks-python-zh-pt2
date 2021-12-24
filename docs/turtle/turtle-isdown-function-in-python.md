# Python 中的 turtle.isdown()函数

> 原文:[https://www . geesforgeks . org/turtle-is down-function-in-python/](https://www.geeksforgeeks.org/turtle-isdown-function-in-python/)

海龟模块以面向对象和面向过程的方式提供海龟图形原语。因为它使用 Tkinter 作为底层图形，所以它需要安装一个支持 Tk 的 Python 版本。

## turtle.isdown()

这个方法是用来检查乌龟是否下来了。它不需要任何参数，如果笔是向下的，返回布尔值为真，如果笔是向上的，返回 False。

**语法:**

```
turtle.isdown()

```

下面是上面方法的实现:

## 蟒 3

```
# import package
import turtle 

# to check
print(turtle.isdown())
turtle.forward(10)

# up the turtle
turtle.up()

# to check
print(turtle.isdown())

# up the turtle
turtle.down()
turtle.forward(10)

# to check
print(turtle.isdown())
```

**输出:**

```
True
False
True

```