# 使用 Python 中的海龟图形绘制熊猫

> 原文:[https://www . geesforgeks . org/draw-panda-use-turtle-graphics-in-python/](https://www.geeksforgeeks.org/draw-panda-using-turtle-graphics-in-python/)

海龟是 Python 中的一个内置模块。它规定:

1.  使用屏幕(纸板)绘图。
2.  乌龟(钢笔)。

要在屏幕上画东西，我们需要移动乌龟(笔)，而要移动乌龟，有一些功能，比如前进()，后退()，等等。

**先决条件:** [海龟编程基础知识](https://www.geeksforgeeks.org/turtle-programming-python/)

### 用乌龟图形画熊猫

在这一节中，我们将讨论如何使用海龟图形绘制熊猫。

**进场:**

> 1.  *Imported soft-shelled turtle.*
> 2.  *Make turtle-shaped objects.*
> 3.  *Define a method of drawing a circle with dynamic radius and color.*
> 4.  *Draw panda ears with black circles.*
> 5.  *Draw the panda face with a white circle.*
> 6.  *Draw the panda's eyes with black and white concentric circles.*
> 7.  *Draw the panda's nose with a black circle.*
> 8.  *Draw two semicircles under the nose as the mouth.* T32】T33

**代码:**

## 蟒蛇 3

```py
# Draw a Panda using Turtle Graphics
# Import turtle package
import turtle

# Creating a turtle object(pen)
pen = turtle.Turtle()

# Defining method to draw a colored circle 
# with a dynamic radius
def ring(col, rad):

    # Set the fill
    pen.fillcolor(col)

    # Start filling the color
    pen.begin_fill()

    # Draw a circle
    pen.circle(rad)

    # Ending the filling of the color
    pen.end_fill()

##########################Main Section#############################

# pen.up             --> move turtle to air
# pen.down           --> move turtle to ground
# pen.setpos         --> move turtle to given position
# ring(color, radius) --> draw a ring of specified color and radius
###################################################################

##### Draw ears #####
# Draw first ear
pen.up()
pen.setpos(-35, 95)
pen.down
ring('black', 15)

# Draw second ear
pen.up()
pen.setpos(35, 95)
pen.down()
ring('black', 15)

##### Draw face #####
pen.up()
pen.setpos(0, 35)
pen.down()
ring('white', 40)

##### Draw eyes black #####

# Draw first eye
pen.up()
pen.setpos(-18, 75)
pen.down
ring('black', 8)

# Draw second eye
pen.up()
pen.setpos(18, 75)
pen.down()
ring('black', 8)

##### Draw eyes white #####

# Draw first eye
pen.up()
pen.setpos(-18, 77)
pen.down()
ring('white', 4)

# Draw second eye
pen.up()
pen.setpos(18, 77)
pen.down()
ring('white', 4)

##### Draw nose #####
pen.up()
pen.setpos(0, 55)
pen.down
ring('balck', 5)

##### Draw mouth #####
pen.up()
pen.setpos(0, 55)
pen.down()
pen.right(90)
pen.circle(5, 180)
pen.up()
pen.setpos(0, 55)
pen.down()
pen.left(360)
pen.circle(5, -180)
pen.hideturtle()
```

**输出:**

![Panda Using Turtle Graphics](img/ced2c5dbbc69b795798442862a7c379e.png)