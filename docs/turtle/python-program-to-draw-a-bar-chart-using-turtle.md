# Python 程序使用海龟绘制条形图

> 原文:[https://www . geesforgeks . org/python-程序-绘制条形图-使用-海龟/](https://www.geeksforgeeks.org/python-program-to-draw-a-bar-chart-using-turtle/)

**先决条件:** [海龟编程基础知识](https://www.geeksforgeeks.org/turtle-programming-python/)

**乌龟**是画板一样的 Python 特性，让我们命令一只乌龟在上面画个遍！我们可以使用像乌龟一样的功能。前进(…)和乌龟。右(…)可以移动乌龟。海龟是一种初学者友好的学习 Python 的方法，通过运行一些基本命令并查看海龟的图形来完成。它就像一个画板，可以让你在上面画画。海龟模块可以以面向对象和面向过程的方式使用。

为了绘图，Python turtle 提供了很多功能和方法，即向前、向后等。一些常用的方法有:

*   **向前(x)** :向前移动笔 x 个单位。
*   **向后(x)** :将笔向后移动 x 个单位。
*   **右(x)** :顺时针方向旋转笔 x 角度。
*   **左(x)** :逆时针方向旋转笔 x 角度。
*   **penip()**:停止龟笔的绘制。
*   **pendown()** :开始画龟笔。

海龟可以用来画任何静态的形状(可以用线画的形状)。我们都知道

**进场:**

*   导入海龟库。
*   创建一个[函数](https://www.geeksforgeeks.org/functions-in-c/)，比如说**拉杆()**，获取一个乌龟对象、一个高度值和一个颜色名称，并执行以下步骤:
    *   该函数绘制给定高度和固定宽度的垂直矩形(比如 **40** )。
    *   该函数用给定的颜色名称填充矩形。
*   初始化一个包含一些数值(条形图数据)的列表。
*   初始化一个海龟实例。
*   设置窗口，为列表中的每个值调用**拉杆()**，并创建海龟实例和您选择的任何颜色。
*   完成上述步骤后，关闭海龟实例。

下面是上述方法的实现:

## 蟒蛇 3

```
# Python program to draw a turtle
import turtle

# Function that draws the turtle
def drawBar(t, height, color):

    # Get turtle t to draw one bar
    # of height

    # Start filling this shape
    t.fillcolor(color)
    t.begin_fill()             
    t.left(90)
    t.forward(height)
    t.write(str(height))
    t.right(90)
    t.forward(40)
    t.right(90)
    t.forward(height)
    t.left(90)

    # stop filling the shape
    t.end_fill()                

# Driver Code

xs = [48, 117, 200, 96, 134, 260, 99]
clrs = ["green", "red", "yellow", "black",
        "pink", "brown", "blue"]

maxheight = max(xs)
numbers = len(xs)
border = 10

# Set up the window and its
# attributes
wn = turtle.Screen()            
wn.setworldcoordinates(0 - border, 0 - border,
                       40 * numbers + border,
                       maxheight + border)

# Create tess and set some attributes
tess = turtle.Turtle()          
tess.pensize(3)

for i in range(len(xs)):

    drawBar (tess, xs[i],
             clrs[i])

wn.exitonclick()
```

**输出:**

<video class="wp-video-shortcode" id="video-521718-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201128205058/bar-turtle.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201128205058/bar-turtle.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201128205058/bar-turtle.mp4)</video>