# 使用 Python 中的 Turtle 绘制汽车

> 原文:[https://www . geeksforgeeks . org/draw-a-car-use-turtle-in-python/](https://www.geeksforgeeks.org/draw-a-car-using-turtle-in-python/)

**先决条件:** [龟模](https://www.geeksforgeeks.org/turtle-programming-python/)[绘制形状](https://www.geeksforgeeks.org/draw-shape-inside-shape-in-python-using-turtle/)

python 中有很多描绘图形插图的模块，其中之一就是*龟*，它是 Python 中的内置模块，让用户控制一支笔(*龟*)在屏幕(画板)上进行绘制。它主要用于说明图形、形状、设计等。在本文中，我们将学习如何使用*龟*模块绘制汽车。

**使用** ***龟*** **模块在 Python 中绘制汽车:**

1.  我们将使用*龟*模块来创建不同的形状，以便说明一辆汽车。
2.  可以使用*圆()*功能绘制轮胎。
3.  上半身可以想象成一个长方形。
4.  屋顶和窗户类似梯形。
5.  将上述所有形状重叠在特定位置将会显示一辆汽车。

**让我们借助下面的程序来尝试更好地理解它:**

## 蟒蛇 3

```
#Python program to draw car in turtle programming

# Import required library 
import turtle

car = turtle.Turtle()

# Below code for drawing rectangular upper body
car.color('#008000')
car.fillcolor('#008000')
car.penup()
car.goto(0,0)
car.pendown()
car.begin_fill()
car.forward(370)
car.left(90)
car.forward(50)
car.left(90)
car.forward(370)
car.left(90)
car.forward(50)
car.end_fill()

# Below code for drawing window and roof
car.penup()
car.goto(100, 50)
car.pendown()
car.setheading(45)
car.forward(70)
car.setheading(0)
car.forward(100)
car.setheading(-45)
car.forward(70)
car.setheading(90)
car.penup()
car.goto(200, 50)
car.pendown()
car.forward(49.50)

# Below code for drawing two tyres
car.penup()
car.goto(100, -10)
car.pendown()
car.color('#000000')
car.fillcolor('#000000')
car.begin_fill()
car.circle(20)
car.end_fill()
car.penup()
car.goto(300, -10)
car.pendown()
car.color('#000000')
car.fillcolor('#000000')
car.begin_fill()
car.circle(20)
car.end_fill()

car.hideturtle()
```

**输出:**

<video class="wp-video-shortcode" id="video-484631-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200911223428/car.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200911223428/car.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200911223428/car.mp4)</video>