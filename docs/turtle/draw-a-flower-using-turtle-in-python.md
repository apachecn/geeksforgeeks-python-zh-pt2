# 用蟒蛇皮画一朵花

> 原文:[https://www . geesforgeks . org/draw-a-flower-using-turtle-in-python/](https://www.geeksforgeeks.org/draw-a-flower-using-turtle-in-python/)

**先决条件:**[Python 中的海龟编程](https://www.geeksforgeeks.org/turtle-programming-python/)

乌龟是 Python 的一个功能，就像画板一样，让我们命令一只乌龟在上面画来画去！我们可以使用像 turtle.forward(…)和 turtle.right(…)这样的函数来移动乌龟。海龟是一种初学者友好的学习 Python 的方法，通过运行一些基本命令并查看海龟的图形来完成。它就像一个画板，可以让你在上面画画。海龟模块可以以面向对象和面向过程的方式使用。
画图，Python 龟提供了很多功能和方法，即前进、后退等。一些常用的方法有:

*   **向前(x):** 向前移动笔 x 个单位。

*   **向后(x):** 将笔向后移动 x 个单位。

*   **右(x):** 顺时针方向旋转笔一个角度 x。

*   **左(x):** 逆时针旋转笔一个角度 x。

*   **penip():**停止龟笔的绘制。

*   **pendown():** 开始画龟笔。

在本文中，我们将借助海龟编程编写一个绘制花朵的代码。如下图所示。

**进场:**

*   导入海龟模块
*   设定乌龟的速度
*   使用循环来避免不必要的代码重复。
*   用特定的坐标画出每一步

下面是实现:

**示例 1:-花**

## 蟒蛇 3

```
import turtle

tur = turtle.Turtle()
tur.speed(20)
tur.color("black", "orange")
tur.begin_fill()

for i in range(50):
    tur.forward(300)
    tur.left(170)

tur.end_fill()
turtle.done()
```

**输出:**

<video class="wp-video-shortcode" id="video-481347-1" width="640" height="360" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200907132532/flower-turrle.webm?_=1">[https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200907132532/flower-turrle.webm](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200907132532/flower-turrle.webm)</video>

**例 2:**

## 蟒蛇 3

```
import turtle

# Set initial position
turtle.penup ()
turtle.left (90)
turtle.fd (200)
turtle.pendown ()
turtle.right (90)

# flower base
turtle.fillcolor ("red")
turtle.begin_fill ()
turtle.circle (10,180)
turtle.circle (25,110)
turtle.left (50)
turtle.circle (60,45)
turtle.circle (20,170)
turtle.right (24)
turtle.fd (30)
turtle.left (10)
turtle.circle (30,110)
turtle.fd (20)
turtle.left (40)
turtle.circle (90,70)
turtle.circle (30,150)
turtle.right (30)
turtle.fd (15)
turtle.circle (80,90)
turtle.left (15)
turtle.fd (45)
turtle.right (165)
turtle.fd (20)
turtle.left (155)
turtle.circle (150,80)
turtle.left (50)
turtle.circle (150,90)
turtle.end_fill ()

# Petal 1
turtle.left (150)
turtle.circle (-90,70)
turtle.left (20)
turtle.circle (75,105)
turtle.setheading (60)
turtle.circle (80,98)
turtle.circle (-90,40)

# Petal 2
turtle.left (180)
turtle.circle (90,40)
turtle.circle (-80,98)
turtle.setheading (-83)

# Leaves 1
turtle.fd (30)
turtle.left (90)
turtle.fd (25)
turtle.left (45)
turtle.fillcolor ("green")
turtle.begin_fill ()
turtle.circle (-80,90)
turtle.right (90)
turtle.circle (-80,90)
turtle.end_fill ()
turtle.right (135)
turtle.fd (60)
turtle.left (180)
turtle.fd (85)
turtle.left (90)
turtle.fd (80)

# Leaves 2
turtle.right (90)
turtle.right (45)
turtle.fillcolor ("green")
turtle.begin_fill ()
turtle.circle (80,90)
turtle.left (90)
turtle.circle (80,90)
turtle.end_fill ()
turtle.left (135)
turtle.fd (60)
turtle.left (180)
turtle.fd (60)
turtle.right (90)
turtle.circle (200,60)
turtle.done()
```

**输出:**

<video class="wp-video-shortcode" id="video-481347-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200920125256/Rose.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200920125256/Rose.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200920125256/Rose.mp4)</video>