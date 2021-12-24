# Python 中的 turtle.setx()函数

> 原文:[https://www . geesforgeks . org/turtle-setx-function-in-python/](https://www.geeksforgeeks.org/turtle-setx-function-in-python/)

海龟模块以面向对象和面向过程的方式提供海龟图形原语。因为它使用 tkinter 作为底层图形，所以需要安装一个支持 Tk 的 Python 版本。

## turtle.setx()

这个方法用于将海龟的第一个坐标设置为 x，保持第二个坐标不变。在这里，不管乌龟的位置是什么，它都将 x 坐标设置为给定的输入，保持 y 坐标不变。

> **语法:** turtle.setx(x)
> 
> **参数:**
> 
> **x:** 一个数字(整数或浮点数)，它是唯一需要的参数。

下面是上述方法的实现，并附有一些例子:

**例 1 :**

## 蟒蛇 3

```
# import package
import turtle

# check the turtle position
print(turtle.position())

# set the x coordinate
turtle.setx(30)

# check the turtle position
print(turtle.position())

# set the x coordinate
turtle.setx(-50)

# check the turtle position
print(turtle.position())
```

**输出:**

```
(0.0, 0.0)
(30.0, 0.0)
(-50.0, 0.0)
```

**例 2 :**

## 蟒蛇 3

```
# import package
import turtle

# set turtle direction
turtle.left(90)

# loop for pattern
for i in range(4):

  # motion
  turtle.forward(100)
  turtle.right(90)
  turtle.forward(20)
  turtle.right(90)
  turtle.forward(100)

  # set the x coordinate
  turtle.up()
  turtle.setx(40*(i+1))
  turtle.down()

  # change the direction
  turtle.left(180)
```

**输出:**

![](img/552dfa82552c0934d865aef47588666d.png)