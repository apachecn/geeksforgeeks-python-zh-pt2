# 使用 Python 中的海龟模块绘制一个小屋

> 原文:[https://www . geesforgeks . org/draw-a-hut-using-turtle-module-in-python/](https://www.geeksforgeeks.org/draw-a-hut-using-turtle-module-in-python/)

[Turtle](https://www.geeksforgeeks.org/turtle-programming-python/) 是 Python 中的内置模块，有 forward()、backward()、right()和 left()等多种功能。只需使用 Python 中的海龟模块，就可以在屏幕上绘制一个小屋。在本文中，我们将使用海龟模块创建一个小屋。

**进场:**

1.  进口海龟
2.  设置背景颜色。
3.  定义一个函数来绘制小屋的前部，即矩形。
4.  定义一个绘制小屋顶部的函数，即等边三角形。
5.  定义一个绘制小屋侧面部分的函数，即平行四边形。
6.  使用 penup()和 pendown()函数为小屋绘制窗户和门。
7.  在小屋中填充适当的颜色。

下面是实现。

## 蟒蛇 3

```
import turtle
import math

# Set the background color
screen = turtle.Screen()
screen.bgcolor("lightpink")

# Create our turtle
t = turtle.Turtle()
t.color("black")
t.shape("turtle")
t.speed(5)

# Define a function to draw and
# fill a rectangle with the given
# dimensions and color
def drawRectangle(t, width, height, color):

    t.fillcolor(color)
    t.begin_fill()
    t.forward(width)
    t.left(90)
    t.forward(height)
    t.left(90)
    t.forward(width)
    t.left(90)
    t.forward(height)
    t.left(90)
    t.end_fill()

# Define a function to draw and fill an equalateral right
# triangle with the given hypotenuse length and color.  This
# is used to create a roof shape.
def drawTriangle(t, length, color):
    t.fillcolor(color)
    t.begin_fill()
    t.forward(length)
    t.left(135)
    t.forward(length / math.sqrt(2))
    t.left(90)
    t.forward(length / math.sqrt(2))
    t.left(135)
    t.end_fill()

# Define a function to draw and fill a parallelogram, used to
# draw the side of the house
def drawParallelogram(t, width, height, color):
    t.fillcolor(color)
    t.begin_fill()
    t.left(30)
    t.forward(width)
    t.left(60)
    t.forward(height)
    t.left(120)
    t.forward(width)
    t.left(60)
    t.forward(height)
    t.left(90)
    t.end_fill()

# Draw and fill the front of the house
t.penup()
t.goto(-150, -120)
t.pendown()
drawRectangle(t, 100, 110, "blue")

# Draw and fill the front door
t.penup()
t.goto(-120, -120)
t.pendown()
drawRectangle(t, 40, 60, "lightgreen")

# Front roof
t.penup()
t.goto(-150, -10)
t.pendown()
drawTriangle(t, 100, "magenta")

# Side of the house
t.penup()
t.goto(-50, -120)
t.pendown()
drawParallelogram(t, 60, 110, "yellow")

# Window
t.penup()
t.goto(-30, -60)
t.pendown()
drawParallelogram(t, 20, 30, "brown")

# Side roof
t.penup()
t.goto(-50, -10)
t.pendown()
t.fillcolor("orange")
t.begin_fill()
t.left(30)
t.forward(60)
t.left(105)
t.forward(100 / math.sqrt(2))
t.left(75)
t.forward(60)
t.left(105)
t.forward(100 / math.sqrt(2))
t.left(45)
t.end_fill()
turtle.done()
```

**输出:**

<video class="wp-video-shortcode" id="video-493928-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200915222323/Hut.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200915222323/Hut.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200915222323/Hut.mp4)</video>