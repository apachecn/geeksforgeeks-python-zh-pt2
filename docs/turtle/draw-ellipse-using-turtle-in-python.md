# 用 Python 中的龟画椭圆

> 原文:[https://www . geeksforgeeks . org/draw-ellips-use-turtle-in-python/](https://www.geeksforgeeks.org/draw-ellipse-using-turtle-in-python/)

**先决条件:** [海龟编程基础知识](https://www.geeksforgeeks.org/turtle-programming-python/)

**海龟**是 Python 中的内置模块。它提供使用屏幕(纸板)和乌龟(钢笔)的绘图。要在屏幕上画东西，我们需要移动乌龟(笔)。要移动海龟，有一些功能，例如向前()，向后()，等等。

**进场:**

使用以下步骤:

*   进口海龟
*   将椭圆分成四个弧
*   定义成对形成这些弧方法
*   调用函数。

下面是实现:

## 蟒蛇 3

```py
# import package
import turtle

# method to draw ellipse
def draw(rad):

  # rad --> radius of arc
  for i in range(2):

    # two arcs
    turtle.circle(rad,90)
    turtle.circle(rad//2,90)

# Main section
# tilt the shape to negative 45
turtle.seth(-45)

# calling draw method
draw(100)
```

**输出:**

![](img/29c38df82583a1eff11b2449056ad534.png)

#### 使用椭圆形状绘制设计

使用以下步骤:

*   进口海龟
*   设置屏幕
*   将椭圆分成四个弧
*   定义成对形成这些弧方法
*   针对不同的颜色多次调用函数。

下面是实现:

## 蟒蛇 3

```py
# import package and making object
import turtle
screen = turtle.Screen()

# method to draw ellipse
def draw(rad):

  # rad --> radius for arc
    for i in range(2):
        turtle.circle(rad,90)
        turtle.circle(rad//2,90)

# Main Section
# Set screen size
screen.setup(500,500)

# Set screen color
screen.bgcolor('black')

# Colors
col=['violet','blue','green','yellow',
     'orange','red']

# some integers
val=10
ind=0

# turtle speed
turtle.speed(100)

# loop for multiple ellipse
for i in range(36):

    # oriented the ellipse at angle = -val
    turtle.seth(-val)

    # color of ellipse
    turtle.color(col[ind])

    # to access different color
    if ind==5:
        ind=0
    else:
        ind+=1

    # calling method
    draw(80)

    # orientation change
    val+=10

# for hiding the turtle
turtle.hideturtle()
```

**输出:**

![](img/4e0622b5fc48c92c32324261c69419a0.png)