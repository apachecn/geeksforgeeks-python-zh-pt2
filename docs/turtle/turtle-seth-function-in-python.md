# Python 中的 turtle.seth()函数

> 原文:[https://www . geesforgeks . org/turtle-Seth-function-in-python/](https://www.geeksforgeeks.org/turtle-seth-function-in-python/)

海龟模块以面向对象和面向过程的方式提供海龟图形原语。因为它使用 Tkinter 作为底层图形，所以它需要安装一个支持 Tk 的 Python 版本。

## turtle.seth()

此方法用于将海龟的方位设置为**到 _angle** 。这个方法只需要一个参数作为角度。

这两个是该方法的别名–**设置标题**、**设置**。

> **语法:** turtle.seth(to_angle)或 turtle.setheading(to_angle)
> 
> **参数:**
> 
> **to_angle:** 一个数字(整数或浮点数)
> 
> 将海龟的方向设置为 to_angle。以下是一些常见的度数方向(标准模式) :
> 
> *   0–东
> *   90 度–北
> *   180 度–西部
> *   270–南部

下面是上述方法的一个示例实现:

**示例:**

## 蟒蛇 3

```py
# import package
import turtle

# set direction at 0
# angle using seth
turtle.seth(0)

# motion
turtle.forward(80)
turtle.write("East")

# back to home
turtle.home()

# set direction at 90
# angle using sethading
turtle.setheading(90)

# motion
turtle.forward(80)
turtle.write("North")

# back to home
turtle.home()

# set direction at 180
# angle using seth
turtle.seth(180)

# motion
turtle.forward(80)
turtle.write("West",align="right")

# back to home
turtle.home()

# set direction at 270
# angle using setheading
turtle.setheading(270)

# motion
turtle.forward(80)
turtle.write("South")

# hide the turtle
turtle.ht()
```

**输出:**

![](img/73e1cbd923cad5213244a53ac0bba8db.png)