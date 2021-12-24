# 使用 Python 中的乌龟绘制点状图案

> 原文:[https://www . geeksforgeeks . org/draw-dot-patterns-use-turtle-in-python/](https://www.geeksforgeeks.org/draw-dot-patterns-using-turtle-in-python/)

**先决条件:** [海龟编程基础知识](https://www.geeksforgeeks.org/turtle-programming-python/)

海龟是 Python 中的一个内置模块。它提供使用屏幕(纸板)和乌龟(钢笔)的绘图。要在屏幕上画东西，我们需要移动乌龟(笔)。要移动海龟，有一些功能，例如向前()，向后()，等等。

#### 1)画点正方形

使用以下步骤:

*   进口海龟
*   做乌龟
*   定义一个用点绘制正方形的函数
*   调用那个函数
*   把乌龟藏起来。

下面是实现:

## 蟒蛇 3

```
# import package and making object
import turtle 

pen = turtle.Turtle()

# method to draw square with dots
# space --> distance between dots
# x     --> side of square
def draw(space,x):
  for i in range(x):
    for j in range(x):

        # dot
        pen.dot()

        # distance for another dot
        pen.forward(space)
    pen.backward(space*x)

    # direction
    pen.right(90)
    pen.forward(space)
    pen.left(90)

# Main Section
pen.penup()
draw(10,8)

# hide the turtle
pen.hideturtle()
```

**输出:**

![](img/8b00779f5763a7eded6db003da124680.png)

#### 2)绘制点矩形

使用以下步骤:

*   进口海龟
*   做乌龟
*   定义一个用点绘制矩形的函数
*   调用那个函数
*   把乌龟藏起来。

下面是实现:

## 蟒蛇 3

```
# import package and making object
import turtle 

pen = turtle.Turtle()

# method to draw rectangle with dots
# space --> distance between dots
# x     --> height of rectangle
# y     --> width of rectangle
def draw(space,x,y):
  for i in range(x):
    for j in range(y):

        # dot
        pen.dot()

        # distance for another dot
        pen.forward(space)
    pen.backward(space*y)

    # direction
    pen.right(90)
    pen.forward(space)
    pen.left(90)

# Main Section
pen.penup()
draw(10,5,12)

# hide the turtle
pen.hideturtle()
```

**输出:**

![](img/f9229d893d35d566cf0d2960b9432fbd.png)

#### 3)画点菱形:

使用以下步骤:

*   进口海龟
*   做乌龟
*   定义一个用点绘制钻石的函数
*   调用那个函数
*   把乌龟藏起来。

下面是实现:

## 蟒蛇 3

```
# import package and making object
import turtle 

pen = turtle.Turtle()

# method to draw diamond with dots
# space --> distance between dots
# x     --> side of diamond
def draw(space,x):
  for i in range(x):
    for j in range(x):

        # dot
        pen.dot()

        # distance for another dot
        pen.forward(space)
    pen.backward(space*x)

    # direction
    pen.right(90)
    pen.forward(space)
    pen.left(90)

# Main Section
pen.penup()

# direction to form diamond
pen.left(45)
draw(10,8)

# hide the turtle
pen.hideturtle()
```

**输出:**

![](img/06eb24437722b0d73b48c427ec9ae414.png)