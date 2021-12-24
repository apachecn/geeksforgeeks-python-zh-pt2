# 如何在 Python-Turtle 中绘制填色星？

> 原文:[https://www . geesforgeks . org/如何绘制填充颜色的蟒蛇皮星形乌龟/](https://www.geeksforgeeks.org/how-to-draw-color-filled-star-in-python-turtle/)

**先决条件:** [海龟编程基础](https://www.geeksforgeeks.org/turtle-programming-python/)[在海龟](https://www.geeksforgeeks.org/draw-color-filled-shapes-in-turtle-python/)中绘制填色形状

海龟是 Python 中的一个内置模块。它提供使用屏幕(纸板)和乌龟(钢笔)的绘图。要在屏幕上画东西，我们需要移动乌龟(笔)。要移动乌龟，有一些功能，即向前()、向后()，等等。

**进场:**

使用以下步骤:

*   进口海龟
*   设置窗口屏幕
*   设定乌龟的颜色
*   形成一颗星
*   用颜色填满星星

下面是实现。

## 蟒蛇 3

```
# importing package
import turtle

# function to draw
# colored star
def colored_star():

    # size of star
    size = 80

    # object color
    turtle.color("red")

    # object width
    turtle.width(4)

    # angle to form star
    angle = 120

    # color to fill
    turtle.fillcolor("yellow")
    turtle.begin_fill()

    # form star
    for side in range(5):
        turtle.forward(size)
        turtle.right(angle)
        turtle.forward(size)
        turtle.right(72 - angle)

    # fill color
    turtle.end_fill()

# Driver code
colored_star()
```

**输出:**

![](img/377854fb64b036e1a90f6855d820f245.png)

因为，从现在开始，你必须学会如何在一颗星星上绘画和填充颜色。所以，让我们用这些知识来尝试一些独特的东西。让我们用一些创造力和编程来营造一个充满星星的夜晚。

## 蟒蛇 3

```
import turtle
from random import randint

window = turtle.Screen()
turtle.bgcolor("black")
turtle.color("yellow")
turtle.speed(0)

def draw_star():
    turns = 6
    turtle.begin_fill()
    while turns>0:
        turtle.forward(25)
        turtle.left(145)
        turns = turns-1
    turtle.end_fill()

nums_stars = 0
while nums_stars <50:
    x=randint(-300,300)
    y=randint(-300,300)
    draw_star()
    turtle.penup()
    turtle.goto(x,y)
    turtle.pendown()
    nums_stars = nums_stars + 1

window.exitonclick()
```

**输出:**

<video class="wp-video-shortcode" id="video-433613-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201006214616/stars-original.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201006214616/stars-original.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201006214616/stars-original.mp4)</video>