# 使用 Python 中的海龟图形绘制心脏

> 原文:[https://www . geesforgeks . org/draw-heart-use-turtle-graphics-in-python/](https://www.geeksforgeeks.org/draw-heart-using-turtle-graphics-in-python/)

海龟是 Python 中的一个内置模块。它规定:

1.  使用屏幕(纸板)绘图。
2.  乌龟(钢笔)。

要在屏幕上画东西，我们需要移动乌龟(笔)，而要移动乌龟，有一些功能，比如向前()，向后()，等等

**先决条件:** [海龟编程基础知识](https://www.geeksforgeeks.org/turtle-programming-python/)

### 使用海龟图形绘制心脏

在本节中，我们将讨论如何使用海龟图形绘制心脏。

**进场:**

> 1.  Import turtle
> 2.  Making turtle objects
> 3.  Define a simple method of drawing curves by moving back and forth.
> 4.  Define a method to draw a heart and fill it with red.
> 5.  Define a method to display part of the text by setting the position.
> 6.  Call all methods in the main section.

**代码:**

## 蟒蛇 3

```py
# Import turtle package
import turtle

# Creating a turtle object(pen)
pen = turtle.Turtle()

# Defining a method to draw curve
def curve():
    for i in range(200):

        # Defining step by step curve motion
        pen.right(1)
        pen.forward(1)

# Defining method to draw a full heart
def heart():

    # Set the fill color to red
    pen.fillcolor('red')

    # Start filling the color
    pen.begin_fill()

    # Draw the left line
    pen.left(140)
    pen.forward(113)

    # Draw the left curve
    curve()
    pen.left(120)

    # Draw the right curve
    curve()

    # Draw the right line
    pen.forward(112)

    # Ending the filling of the color
    pen.end_fill()

# Defining method to write text
def txt():

    # Move turtle to air
    pen.up()

    # Move turtle to a given position
    pen.setpos(-68, 95)

    # Move the turtle to the ground
    pen.down()

    # Set the text color to lightgreen
    pen.color('lightgreen')

    # Write the specified text in 
    # specified font style and size
    pen.write("GeeksForGeeks", font=(
      "Verdana", 12, "bold"))

# Draw a heart
heart()

# Write text
txt()

# To hide turtle
pen.ht()
```

**输出:**

![Heart Using Turtle Graphics](img/be129d3c9b1668b6c2a9352c077aca4e.png)