# 使用 Python 中的 Turtle 编程绘制房屋

> 原文:[https://www . geesforgeks . org/draw-house-use-turtle-programming-in-python/](https://www.geeksforgeeks.org/draw-house-using-turtle-programming-in-python/)

**先决条件:**[Python 中的龟编程](https://www.geeksforgeeks.org/turtle-programming-python/)

“龟”是画板一样的 Python 特性，让我们命令一只龟在上面画满！“海龟”自带标准 Python 包，无需外部安装。

**第一步:**导入 Python 中的乌龟和数学模块。

```
import turtle
import math

```

**第二步:**选择输出屏幕的背景颜色。你可以选择任何颜色，我们会用黄色只是为了让它有吸引力。

```
screen = turtle.Screen()
screen.bgcolor("yellow")

```

**第三步:**选择你的乌龟(笔)的颜色和速度，它会在屏幕上画出房子。

```
t.color("black")
t.shape("turtle")
t.speed(1)

```

**第四步:**现在，我们需要画出你房子的底部，为此，你需要画一个矩形。

只需在 t.fillcolor(')命令中更改颜色名称，就可以填充您选择的任何颜色。

```
t.fillcolor('cyan')
t.begin_fill( )
t.right(90)
t.forward(250)
t.left(90)
t.forward(400)
t.left(90)

t.forward(250)

t.left(90)
t.forward(400)
t.right(90)
t.end_fill()

```

房子的底部是这样的:

<video class="wp-video-shortcode" id="video-485215-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200913124224/Rectangle.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200913124224/Rectangle.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200913124224/Rectangle.mp4)</video>

**第五步:**现在你创建了基础，下一步是创建房子的顶部。为上部画一个三角形，只是为了简单起见。

```
# for creating triangle
# i.e top of the house
t.fillcolor('brown')
t.begin_fill()
t.right(45)
t.forward(200)
t.right(90)
t.forward(200)
t.left(180)
t.forward(200)
t.right(135)
t.forward(259)
t.right(90)
t.forward(142)
t.end_fill()

```

**第六步:**我们必须通过装上门和窗户来保证我们的房子通风。这是代码-

```
# for windows and
# for creating door
t.right(90)
t.forward(400)
t.left(90)
t.forward(50)
t.left(90)
t.forward(150)
t.right(90)
t.forward(200)
t.right(180)
t.forward(200)
t.right(90)
t.forward(200)
t.right(90)
t.forward(150)
t.right(90)
t.forward(200)
t.right(90)
t.forward(150)

t.right(90)
t.forward(100)
t.right(90)
t.forward(150)
t.right(90)
t.forward(100)
t.right(90)
t.forward(75)
t.right(90)
t.forward(200)

```

**完整代码:**

## 蟒蛇 3

```
import turtle

t = turtle.Turtle()

# for background
screen = turtle.Screen()
screen.bgcolor("yellow")

#color and speed
# of turtle
# creating the house
t.color("black")
t.shape("turtle")
t.speed(1)

# for creating base of
# the house
t.fillcolor('cyan')
t.begin_fill()
t.right(90)
t.forward(250)
t.left(90)
t.forward(400)
t.left(90)
t.forward(250)
t.left(90)
t.forward(400)
t.right(90)
t.end_fill()

# for top of
# the house
t.fillcolor('brown')
t.begin_fill()
t.right(45)
t.forward(200)
t.right(90)
t.forward(200)
t.left(180)
t.forward(200)
t.right(135)
t.forward(259)
t.right(90)
t.forward(142)
t.end_fill()

# for door and
# windows
t.right(90)
t.forward(400)
t.left(90)
t.forward(50)
t.left(90)
t.forward(150)
t.right(90)
t.forward(200)
t.right(180)
t.forward(200)
t.right(90)
t.forward(200)
t.right(90)
t.forward(150)
t.right(90)
t.forward(200)
t.right(90)
t.forward(150)
t.right(90)
t.forward(100)
t.right(90)
t.forward(150)
t.right(90)
t.forward(100)
t.right(90)
t.forward(75)
t.right(90)
t.forward(200)
t.right(180)
t.forward(200)
t.right(90)
t.forward(75)
t.left(90)
t.forward(15)
t.left(90)
t.forward(200)
t.right(90)
t.forward(15)
t.right(90)
t.forward(75)
```

**输出:**

<video class="wp-video-shortcode" id="video-485215-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200913125802/House.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200913125802/House.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200913125802/House.mp4)</video>