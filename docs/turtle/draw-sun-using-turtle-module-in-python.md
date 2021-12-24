# 使用 Python 中的 Turtle 模块绘制太阳

> 原文:[https://www . geesforgeks . org/draw-sun-using-turtle-module-in-python/](https://www.geeksforgeeks.org/draw-sun-using-turtle-module-in-python/)

**先决条件:**[Python 中的龟编程](https://www.geeksforgeeks.org/turtle-programming-python/)

在本文中，让我们学习如何使用 Python 中的海龟绘制太阳。海龟是 Python 中的一个内置模块。它通过提供一个屏幕和一只乌龟(笔)作为工具来帮助绘制图案。按照模块中定义的功能移动海龟，如向前()、向后()、向右()、向左()等。会被雇佣。

**进场:**

*   导入海龟模块
*   为海龟设置一个屏幕。
*   实例化一个海龟对象。
*   对于制作太阳，定义一个圆的方法以及半径和颜色。
*   定义创建太阳光线的函数。

下面是上述方法的实现。

## 蟒蛇 3

```
import turtle

screen = turtle.Screen()

# background color
screen.bgcolor("lightpink")

# turtle object
y = turtle.Turtle()

# define function
# for drawing rays of Sun
def drawFourRays(t, length, radius):

    for i in range(4):
        t.penup()
        t.forward(radius)
        t.pendown()
        t.forward(length)
        t.penup()
        t.backward(length + radius)
        t.left(90)

# Draw circle
# to make sun
y.penup()
y.goto(85, 110)
y.fillcolor("yellow")
y.pendown()
y.begin_fill()
y.circle(45)
y.end_fill()

# Use the defined
# function to draw rays
y.penup()
y.goto(85, 169)
y.pendown()
drawFourRays(y, 85, 54)
y.right(45)
drawFourRays(y, 85, 54)
y.left(45)

# To keep the
# output window active
turtle.done()
```

**输出:**

<video class="wp-video-shortcode" id="video-488346-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200915140355/Sun.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200915140355/Sun.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200915140355/Sun.mp4)</video>