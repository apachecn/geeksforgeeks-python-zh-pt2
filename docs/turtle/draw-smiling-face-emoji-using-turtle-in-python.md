# 使用 Python 中的 Turtle 绘制笑脸表情

> 原文:[https://www . geesforgeks . org/draw-笑脸-表情符号-使用-python 中的海龟/](https://www.geeksforgeeks.org/draw-smiling-face-emoji-using-turtle-in-python/)

#### **先决条件:** [**<u>巨蟒龟基础知识</u>**](https://www.geeksforgeeks.org/turtle-programming-python/)

***【乌龟】*** 是 Python 中内置的模块。它提供使用屏幕(纸板)和乌龟(钢笔)的绘图。要在屏幕上画东西，我们需要移动乌龟。要移动海龟，有一些功能，如*前进()，后退()*等。

在本文中，我们将看到如何使用 ***乌龟*** 模块**绘制笑脸表情符号**。

#### 1.)画笑脸:

> 使用以下步骤:
> 
> *   进口海龟。
> *   制作物品。
> *   画一个圆，填充黄色。
> *   用两个圆圈画眼睛，分别填充白色和黑色。
> *   画鼻子的圆圈，填充黑色。
> *   画出嘴巴的半圆。
> *   为舌头画半圆，填红色。

下面是实现:

## 蟒蛇 3

```
# Python program to draw smile
# face emoji using turtle
import turtle

# turtle object
pen = turtle.Turtle()

# function for creation of eye
def eye(col, rad):
    pen.down()
    pen.fillcolor(col)
    pen.begin_fill()
    pen.circle(rad)
    pen.end_fill()
    pen.up()

# draw face
pen.fillcolor('yellow')
pen.begin_fill()
pen.circle(100)
pen.end_fill()
pen.up()

# draw eyes
pen.goto(-40, 120)
eye('white', 15)
pen.goto(-37, 125)
eye('black', 5)
pen.goto(40, 120)
eye('white', 15)
pen.goto(40, 125)
eye('black', 5)

# draw nose
pen.goto(0, 75)
eye('black', 8)

# draw mouth
pen.goto(-40, 85)
pen.down()
pen.right(90)
pen.circle(40, 180)
pen.up()

# draw tongue
pen.goto(-10, 45)
pen.down()
pen.right(180)
pen.fillcolor('red')
pen.begin_fill()
pen.circle(10, 180)
pen.end_fill()
pen.hideturtle()
```

#### 输出:

![](img/13aa91aa9805a1f302299fe13576cee2.png)

笑脸

2.让我们画一个不同的微笑表情符号，上面画的只是为了更好地理解它。

> 使用以下步骤:
> 
> *   进口海龟。
> *   定义笔的大小和宽度。
> *   画一个圆。
> *   用两个圆圈画眼睛，分别填充红色。
> *   画鼻子的三角形..
> *   画出嘴巴的半圆。

以下是相同的实现

## 蟒蛇 3

```
#import module
import turtle

#define pen size
turtle.pensize (5)

#define pen color
turtle.pencolor ("Blue")

#for outer bigger circle
turtle.fillcolor ("red")
turtle.penup ()
turtle.goto (0, -200)
turtle.pendown ()
turtle.circle (200)

#for eyes
turtle.penup ()
turtle.goto (-100,50)
turtle.pendown ()
turtle.begin_fill ()
turtle.circle (17.5)
turtle.end_fill ()
turtle.penup ()
turtle.goto (100,50)
turtle.pendown ()
turtle.begin_fill ()
turtle.circle (17.5)
turtle.end_fill ()

#for nose
turtle.penup ()
turtle.goto (0,50)
turtle.pendown ()
turtle.circle (-70, steps=3)

# for smile
turtle.penup ()
turtle.goto (-100, -70)
turtle.pendown ()
turtle.right (90)
turtle.circle (100,180)
turtle.mainloop ()
```

**输出:**

<video class="wp-video-shortcode" id="video-435424-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201006182948/turtle-emoji.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201006182948/turtle-emoji.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201006182948/turtle-emoji.mp4)</video>