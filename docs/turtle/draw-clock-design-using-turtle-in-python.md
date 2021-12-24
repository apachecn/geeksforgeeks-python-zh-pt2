# 使用 Python 中的海龟绘制时钟设计

> 原文:[https://www . geeksforgeeks . org/draw-clock-design-use-turtle-in-python/](https://www.geeksforgeeks.org/draw-clock-design-using-turtle-in-python/)

#### 先决条件:[<u>Python 中的海龟编程</u>](https://www.geeksforgeeks.org/turtle-programming-python/)

海龟是 Python 中的一个内置模块。它提供使用屏幕(纸板)和乌龟(钢笔)的绘图。要在屏幕上画东西，我们需要移动乌龟(笔)。要移动海龟，有一些功能，例如向前()，向后()，等等。

#### 要绘制时钟设计:

> 使用以下步骤:
> 
> *   进口海龟。
> *   创建屏幕对象并设置屏幕配置。
> *   创建海龟对象，并设置其位置和速度。
> *   画一条虚线，把数字打印成圆形。
> *   画中心，并在其中填充黑色
> *   在要求的位置写上“GFG”和“时钟”。

下面是实现:

## 蟒蛇 3

```py
# import package
import turtle

# create a Screen Object
screen = turtle.Screen()

# Screen configuration
screen.setup(500, 500)

# Make turtle Object
clk = turtle.Turtle()

# set a Turtle object color
clk.color('Green')

# set a Turtle object width
clk.width(4)

def draw_hour_hand():
    clk.penup()
    clk.home()
    clk.right(90)
    clk.pendown()
    clk.forward(100)

# value for numbers in clock
val = 0

# loop for print clock numbers
for i in range(12):
    # increment value by 1
    val += 1

    # move turtle in air
    clk.penup()

    # for circular motion
    clk.setheading(-30 * (i + 3) + 75)

    # move forward for space
    clk.forward(22)

    # move turtle to surface
    clk.pendown()

    # move forward for dash line
    clk.forward(15)

    # move turtle in air
    clk.penup()

    # move forward for space
    clk.forward(20)

    # write clock integer
    clk.write(str(val), align="center",
              font=("Arial",
                    12, "normal"))

# colored centre by setting position
# sets position of turtle at given position
clk.setpos(2, -112)
clk.pendown()
clk.width(2)

# To fill color green
clk.fillcolor('Green')

# start filling
clk.begin_fill()

# make a circle of radius 5
clk.circle(5)

# end filling
clk.end_fill()

clk.penup()
draw_hour_hand()
clk.setpos(-20, -64)
clk.pendown()
clk.penup()

# Write Clock by setting position
clk.setpos(-30, -170)
clk.pendown()
clk.write(' GfG Clock', font=("Arial", 14,
                              "normal"))
clk.hideturtle()
turtle.done()
```

**输出:**

<video class="wp-video-shortcode" id="video-435695-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20210715165623/clock.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/cdn-uploads/20210715165623/clock.mp4](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20210715165623/clock.mp4)</video>