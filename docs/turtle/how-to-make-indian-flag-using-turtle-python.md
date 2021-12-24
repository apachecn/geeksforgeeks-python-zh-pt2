# 如何用龟蟒制作印度国旗

> 原文:[https://www . geesforgeks . org/如何制作印度国旗-使用海龟-蟒蛇/](https://www.geeksforgeeks.org/how-to-make-indian-flag-using-turtle-python/)

在这里，我们将使用巨蟒龟图形制作“伟大的印度国旗”。在这里，我们将使用许多龟函数，如 **begin_fill()，end_fill()** 来填充旗帜内的颜色， **penup()，pendown()，goto()等**来到达目标。

### 海龟图形

在计算机图形学中，海龟图形是在笛卡尔平面上使用相对光标的矢量图形。乌龟是一种画图板状特征让让我们指挥乌龟用它画画。

> **龟纹特征:**
> 
> *   **向前(x):** 向前移动笔 x 个单位。
> *   **向后(x):** 向后移动笔 x 个单位。
> *   **右(x):** 顺时针方向旋转笔 x 角度。
> *   **左(x):** 逆时针方向旋转笔 x 角度。
> *   **penip():**停止龟笔的绘制。
> *   **pendown():** 开始画龟笔。
> *   **begin_fill():** 开始填充形状内部的颜色。
> *   **fill color(“color _ name”):**设置要填充的颜色。
> *   **end_fill():** 停止填充颜色。

## 方法

1.导入海龟模块。

```
import turtle
```

2.找个屏幕来画画。

```
screen = turtle.Screen()
```

3.为**龟(此处为“t”)定义一个实例。**

4.制作一面**印度国旗**我们把流程分成 4 步:

*   橙色的**矩形。**
*   然后是**中间的矩形。**
*   然后是最后一个**绿色矩形。**
*   然后**阿育王脉轮**在中间长方形里面。

5.这里，所有三个矩形的尺寸都是(800 个单位 x 167 个单位)，这构成了标志 as 的尺寸(800 个单位 x 501 个单位)。

6.乌龟从坐标(-400，250)开始。

7.然后从那个位置开始，它制作第一个橙色矩形颜色**。**

8.然后从第一个矩形**、** **的结束点开始，龟使**成为第二个没有颜色的**矩形**。****

9.然后制作**第三个绿色矩形。**现在对于**阿育王脉轮**、**我们需要执行**一套**操作**

*   一个蓝色的大圆和一个比蓝色小的白色圆。
*   蓝白圈内层的一组蓝色小圈。
*   最后辐条内的两个蓝白圈开始从中心向外的方向。

10.最后，一个国家的骄傲已经准备好了。

下面是上述方法的实现:

## 计算机编程语言

```
import turtle
from turtle import*

#screen for output
screen = turtle.Screen()

# Defining a turtle Instance
t = turtle.Turtle()
speed(0)

# initially penup()
t.penup()
t.goto(-400, 250)
t.pendown()

# Orange Rectangle
#white rectangle
t.color("orange")
t.begin_fill()
t.forward(800)
t.right(90)
t.forward(167)
t.right(90)
t.forward(800)
t.end_fill()
t.left(90)
t.forward(167)

# Green Rectangle
t.color("green")
t.begin_fill()
t.forward(167)
t.left(90)
t.forward(800)
t.left(90)
t.forward(167)
t.end_fill()

# Big Blue Circle
t.penup()
t.goto(70, 0)
t.pendown()
t.color("navy")
t.begin_fill()
t.circle(70)
t.end_fill()

# Big White Circle
t.penup()
t.goto(60, 0)
t.pendown()
t.color("white")
t.begin_fill()
t.circle(60)
t.end_fill()

# Mini Blue Circles
t.penup()
t.goto(-57, -8)
t.pendown()
t.color("navy")
for i in range(24):
    t.begin_fill()
    t.circle(3)
    t.end_fill()
    t.penup()
    t.forward(15)
    t.right(15)
    t.pendown()

# Small Blue Circle
t.penup()
t.goto(20, 0)
t.pendown()
t.begin_fill()
t.circle(20)
t.end_fill()
# Spokes
t.penup()
t.goto(0, 0)
t.pendown()
t.pensize(2)
for i in range(24):
    t.forward(60)
    t.backward(60)
    t.left(15)

#to hold the
#output window
turtle.done()
```

**输出:**

<video class="wp-video-shortcode" id="video-416130-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200925192638/Indian-Flag.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200925192638/Indian-Flag.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200925192638/Indian-Flag.mp4)</video>