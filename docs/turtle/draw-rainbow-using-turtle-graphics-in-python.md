# 使用 Python 中的海龟图形绘制彩虹

> 原文:[https://www . geesforgeks . org/draw-rainbow-use-turtle-graphics-in-python/](https://www.geeksforgeeks.org/draw-rainbow-using-turtle-graphics-in-python/)

海龟是 Python 中的一个内置模块。它规定:

1.  使用屏幕(纸板)绘图。
2.  乌龟(钢笔)。

要在屏幕上画东西，我们需要移动乌龟(笔)，而要移动乌龟，有一些功能，比如前进()，后退()，等等。

**先决条件:** [海龟编程基础知识](https://www.geeksforgeeks.org/turtle-programming-python/)

### 使用海龟图形绘制彩虹

在本节中，我们将讨论如何使用两种不同的方法使用海龟图形绘制彩虹。

**进场:**

> 1.  Imported turtle.
> 2.  Setup screen
> 3.  Make turtle-shaped objects
> 4.  Define for drawing
> 5.  The color of the arc to draw a semicircle oriented at 180 degrees.

**例 1:**

## 蟒蛇 3

```
# Import turtle package
import turtle

# Creating a turtle screen object
sc = turtle.Screen()

# Creating a turtle object(pen)
pen = turtle.Turtle()

# Defining a method to form a semicircle
# with a dynamic radius and color
def semi_circle(col, rad, val):

    # Set the fill color of the semicircle
    pen.color(col)

    # Draw a circle
    pen.circle(rad, -180)

    # Move the turtle to air
    pen.up()

    # Move the turtle to a given position
    pen.setpos(val, 0)

    # Move the turtle to the ground
    pen.down()

    pen.right(180)

# Set the colors for drawing
col = ['violet', 'indigo', 'blue',
       'green', 'yellow', 'orange', 'red']

# Setup the screen features
sc.setup(600, 600)

# Set the screen color to black
sc.bgcolor('black')

# Setup the turtle features
pen.right(90)
pen.width(10)
pen.speed(7)

# Loop to draw 7 semicircles
for i in range(7):
    semi_circle(col[i], 10*(
      i + 8), -10*(i + 1))

# Hide the turtle
pen.hideturtle()
```

**输出:**

![Rainbow using Turtle Graphics](img/612e7914ba4cdf9c8659018c484fb4cd.png)

**例 2:**

## 蟒蛇 3

```
import turtle

mypen= turtle.Turtle()
mypen.shape('turtle')
mypen.speed(10)

window= turtle.Screen()
window.bgcolor('white')
rainbow= ['red','orange','yellow','green','blue','indigo','violet']
size= 180
mypen.penup()
mypen.goto(0,-180)
for color in rainbow:
    mypen.color(color)
    mypen.fillcolor(color)
    mypen.begin_fill()
    mypen.circle(size)
    mypen.end_fill()
    size-=20

turtle.done()
```

**输出:**

<video class="wp-video-shortcode" id="video-436667-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201013162339/Mooreee.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201013162339/Mooreee.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201013162339/Mooreee.mp4)</video>