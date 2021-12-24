# 使用 Python-Turtle 创建数字钟

> 原文:[https://www . geesforgeks . org/create-digital-clock-use-python-turtle/](https://www.geeksforgeeks.org/create-digital-clock-using-python-turtle/)

**先决条件:**[Python 中的海龟编程](https://www.geeksforgeeks.org/turtle-programming-python/)
[**海龟**](https://www.geeksforgeeks.org/turtle-programming-python/) 是 Python 的一个特色。使用海龟，我们可以很容易地在画板上画画。首先，我们导入海龟模块。然后创建一个窗口，接下来我们创建一个海龟对象，并使用海龟方法，我们可以在画板中绘制。
**安装:**要安装该模块，请在终端中键入以下命令。

```
pip install turtle
```

**注意:**要创建时钟，我们还将使用 Python 的‘time’和‘DateTime’模块，要安装时间，请使用以下命令:

下面是实现。

## 蟒蛇 3

```
import time
import datetime as dt
import turtle

# create a turtle to display time
t = turtle.Turtle()

# create a turtle to create rectangle box
t1 = turtle.Turtle()

# create screen
s = turtle.Screen()

# set background color of the screen
s.bgcolor("green")

# obtain current hour, minute and second
# from the system
sec = dt.datetime.now().second
min = dt.datetime.now().minute
hr = dt.datetime.now().hour
t1.pensize(3)
t1.color('black')
t1.penup()

# set the position of turtle
t1.goto(-20, 0)
t1.pendown()

# create rectangular box
for i in range(2):
    t1.forward(200)
    t1.left(90)
    t1.forward(70)
    t1.left(90)

# hide the turtle
t1.hideturtle()

while True:
    t.hideturtle()
    t.clear()
    # display the time
    t.write(str(hr).zfill(2)
            +":"+str(min).zfill(2)+":"
            +str(sec).zfill(2),
            font =("Arial Narrow", 35, "bold"))
    time.sleep(1)
    sec+= 1

    if sec == 60:
        sec = 0
        min+= 1

    if min == 60:
        min = 0
        hr+= 1

    if hr == 13:
        hr = 1
```

**输出:**

<video class="wp-video-shortcode" id="video-430449-1" width="640" height="360" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/uploads/20200612210551/python-digital-clock-turtle.webm?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200612210551/python-digital-clock-turtle.webm](https://media.geeksforgeeks.org/wp-content/uploads/20200612210551/python-digital-clock-turtle.webm)</video>