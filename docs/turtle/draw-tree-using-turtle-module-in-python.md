# 使用 Python 中的 Turtle 模块绘制树

> 原文:[https://www . geesforgeks . org/draw-tree-use-turtle-module-in-python/](https://www.geeksforgeeks.org/draw-tree-using-turtle-module-in-python/)

**先决条件:** [龟模](https://www.geeksforgeeks.org/turtle-programming-python/)[画三角形](https://www.geeksforgeeks.org/how-to-make-triangle-in-python-turtle-using-onscreenclick/)[画矩形](https://www.geeksforgeeks.org/draw-square-and-rectangle-in-turtle-python/)

python 中有很多描绘图形插图的模块，其中之一就是*龟*，它是 Python 中的内置模块，让用户控制一支笔(*龟*)在屏幕(画板)上进行绘制。它主要用于说明图形、形状、设计等。在本文中，我们将学习如何使用*海龟*模块绘制一棵简单的树。图解一棵树包括创建一个矩形，然后从底部开始依次创建三个大小相同的三角形。

**以下是创建树的步骤:**

1.  导入*龟*和*数学*模块。
2.  设置屏幕尺寸和颜色。
3.  创建一个*龟*对象。
4.  通过图示堆叠的三角形和矩形来创建树。

**以下是上述方法的程序:**

## 蟒蛇 3

```py
# Python program to draw a tree using turtle 
# Importing required modules
import turtle
import math

# Function to draw rectangle
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

# Function to draw triangle    
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

# Set the background color
screen = turtle.Screen ( )
screen.bgcolor("skyblue")

# Creating turtle object
tip = turtle.Turtle()
tip.color ("black")
tip.shape ("turtle")
tip.speed (2)

# Tree base
tip.penup()
tip.goto(100, -130)
tip.pendown()
drawRectangle(tip, 20, 40, "brown")

# Tree top
tip.penup()
tip.goto(65, -90)
tip.pendown()
drawTriangle(tip, 90, "lightgreen")
tip.penup()
tip.goto(70, -45)
tip.pendown()
drawTriangle(tip, 80, "lightgreen")
tip.penup()
tip.goto(75, -5)
tip.pendown()
drawTriangle(tip, 70, "lightgreen")
```

**输出:-**

<video class="wp-video-shortcode" id="video-485275-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200914172757/tree.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200914172757/tree.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200914172757/tree.mp4)</video>