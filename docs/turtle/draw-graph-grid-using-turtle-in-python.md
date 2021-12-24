# 使用 Python 中的海龟绘制图形网格

> 原文:[https://www . geeksforgeeks . org/draw-graph-grid-use-turtle-in-python/](https://www.geeksforgeeks.org/draw-graph-grid-using-turtle-in-python/)

**先决条件:** [海龟编程基础知识](https://www.geeksforgeeks.org/turtle-programming-python/)

**海龟**是 Python 中的内置模块。它提供使用屏幕(纸板)和乌龟(钢笔)的绘图。要在屏幕上画东西，我们需要移动乌龟(笔)。要移动海龟，有一些功能，例如向前()，向后()，等等。

**进场:**

使用以下步骤:

*   进口海龟
*   设置屏幕
*   做乌龟
*   绘制 y 轴线
*   绘制 x 轴线
*   用标签绘制 x 轴和 y 轴。

下面是实现:

## 蟒蛇 3

```
# import package and making objects
import turtle

sc=turtle.Screen()
trtl=turtle.Turtle()

# method to draw y-axis lines
def drawy(val):

    # line
    trtl.forward(300)

    # set position
    trtl.up()
    trtl.setpos(val,300)
    trtl.down()

    # another line
    trtl.backward(300)

    # set position again
    trtl.up()
    trtl.setpos(val+10,0)
    trtl.down()

# method to draw y-axis lines
def drawx(val):

    # line
    trtl.forward(300)

    # set position
    trtl.up()
    trtl.setpos(300,val)
    trtl.down()

    # another line
    trtl.backward(300)

    # set position again
    trtl.up()
    trtl.setpos(0,val+10)
    trtl.down()

# method to label the graph grid
def lab():

    # set position
    trtl.penup()
    trtl.setpos(155,155)
    trtl.pendown()

    # write 0
    trtl.write(0,font=("Verdana", 12, "bold"))

    # set position again
    trtl.penup()
    trtl.setpos(290,155)
    trtl.pendown()

    # write x
    trtl.write("x",font=("Verdana", 12, "bold"))

    # set position again
    trtl.penup()
    trtl.setpos(155,290)
    trtl.pendown()

    # write y
    trtl.write("y",font=("Verdana", 12, "bold"))

# Main Section
# set screen
sc.setup(800,800)   

# set turtle features
trtl.speed(100)
trtl.left(90) 
trtl.color('lightgreen')

# y lines
for i in range(30):
    drawy(10*(i+1))

# set position for x lines
trtl.right(90)
trtl.up()
trtl.setpos(0,0)
trtl.down()

# x lines
for i in range(30):
    drawx(10*(i+1))

# axis
trtl.color('green')

# set position for x axis
trtl.up()
trtl.setpos(0,150)
trtl.down()

# x-axis
trtl.forward(300)

# set position for y axis
trtl.left(90)
trtl.up()
trtl.setpos(150,0)
trtl.down()

# y-axis
trtl.forward(300)

# labeling
lab()

# hide the turtle
trtl.hideturtle()
```

**输出:**

![](img/19201217e4b7f7bb7e17110b13dd5172.png)