# 用 Python 中的龟模画雪人

> 原文:[https://www . geesforgeks . org/画雪人-使用 python 中的海龟模块/](https://www.geeksforgeeks.org/draw-a-snowman-using-turtle-module-in-python/)

**先决条件:** [龟模](https://www.geeksforgeeks.org/turtle-programming-python/)[绘制形状](https://www.geeksforgeeks.org/draw-shape-inside-shape-in-python-using-turtle/)

python 中有很多描绘图形插图的模块，其中之一就是*龟*，它是 Python 中的内置模块，让用户控制一支笔(*龟*)在屏幕(画板)上进行绘制。它主要用于说明图形、形状、设计等。在本文中，我们将学习如何使用*龟*模块堆雪人。雪人由各种大小的圆形雪球组成。雪人的身体由三个雪球组成，一个放在另一个上面。眼睛、鼻子和纽扣也是圆形的。

**以下是上述方法的步骤:**

1.  进口*龟*包。
2.  设置屏幕尺寸和颜色。
3.  用颜色创建一个*龟*对象。
4.  通过在特定位置画出重叠的圆圈来创造雪人。

**下面是 Python 程序使用** ***乌龟*** **模块来说明雪人:**

## 蟒蛇 3

```
# Import required module
import turtle

# Create turtle object
t = turtle.Turtle()

# Create a screen 
screen =turtle.Screen()

# Set background color
screen.bgcolor("sky blue")

# Function to draw body of snowman
def draw_circle(color, radius, x, y):
    t.penup()
    t.fillcolor (color)
    t.goto (x, y)
    t.pendown()
    t.begin_fill()
    t.circle (radius)
    t.end_fill()

# Illustrating snowman 
# Drawing snowman body
draw_circle ("#ffffff", 30, 0, -40)
draw_circle ("#ffffff", 40, 0, -100)
draw_circle ("#ffffff", 60, 0, -200)

# Drawing left eye
draw_circle ("#ffffff", 2, -10, -10) 

# Drawing right eye
draw_circle ("#ffffff", 2, 10, -10) 

# Drawing nose
draw_circle ("#FF6600", 3, 0, -15)  

# Drawing buttons on
draw_circle ("#ffffff", 2, 0, -35)
draw_circle ("#ffffff", 2, 0, -45)
draw_circle ("#ffffff", 2, 0, -55)

# Function to draw arms 
def create_line(x, y, length, angle):
    t.penup()
    t.goto(x, y)
    t.setheading(angle)
    t.pendown()
    t.forward(length)
    t.setheading(angle + 20)
    t.forward(20)
    t.penup()
    t.back(20)
    t.pendown()
    t.setheading(angle - 20)
    t.forward(20)
    t.penup()
    t.home()

# Drawing left arm
create_line(-70, -50, 50, 160) 

# Drawing right arm
create_line(70, -50, 50, 20) 

# Drawing hat
t.penup()
t.goto (-35, 8)
t.color ("black")
t.pensize (6)
t.pendown()
t.goto (35, 8)

t.goto (30, 8)
t.fillcolor ("black")
t.begin_fill()
t.left (90)
t.forward (15)
t.left (90)
t.forward (60)
t.left (90)
t.forward (15)
t.end_fill()
```

**输出:**

<video class="wp-video-shortcode" id="video-485158-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200913165702/Snowman.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200913165702/Snowman.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200913165702/Snowman.mp4)</video>