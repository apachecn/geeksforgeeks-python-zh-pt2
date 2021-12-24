# 巨蟒龟–图形键盘命令

> 原文:[https://www . geesforgeks . org/python-海龟-图形-键盘-命令/](https://www.geeksforgeeks.org/python-turtle-graphics-keyboard-commands/)

Python [Turtle](https://www.geeksforgeeks.org/turtle-programming-python/) 模块是一个图形工具，可以使用光标在屏幕上绘制简单的图形。Python Turtle 是 Logo 编程语言的一部分，它有类似的目的，让用户借助简单的命令在屏幕上绘制图形。海龟是一个预装的模块，有内置的命令和功能，可以用来在屏幕上画画。本文将主要关注使用键盘命令创建图形，以及如何使用相同的方法来添加或更改图形的颜色。

### 使用的功能:

*   **Screen()**–用于创建绘图画布
*   **海龟运动:**
    *   **向前(距离)| fd(距离)**:向前移动乌龟
    *   **向后(距离)|向后(距离)| bk(距离)**:将乌龟向后移动
    *   **右(距离)| rt(距离)**:向右移动乌龟
    *   **左移(距离)| lt(距离)**:将乌龟左移
    *   **圆(半径)**:画一个给定半径的圆
*   **着色:**
    *   **颜色()**:设置颜色
    *   **begin_fill()** :在绘制要填充的形状之前调用该方法
    *   **end_fill()** :填充调用 begin_fill()后绘制的形状。

下面给出了两种处理和讨论如何创建图形键盘的方法

### 方法 1

**接近**

*   导入模块和子模块
*   创建设置-setup()方法设置一个大小为 500×500 的窗口。
*   创建窗口 Screen()方法为绘图创建一个画布。
*   实例化海龟对象
*   将龟速设置为 0，这是最大值
*   设置可见性 showturtle()方法设置海龟的可见性。
*   为了捕捉击键，我们需要定义几个函数，即上、下、左、右。默认情况下，乌龟指向右边。
    *   setheading()方法将海龟的方向更改为给定的角度。
    *   forward()方法将海龟移动到指定的距离。
    *   listen()方法将焦点设置在海龟屏幕上以捕获事件。
    *   onkey()方法调用特定于捕获的击键的方法。onkey()的第一个参数是要调用的函数，第二个参数是键。
    *   向上、向下、向左和向右是键盘上相应的箭头键。
*   Add mainloop()命令，它防止应用程序在用户真正单击退出选项之前终止。

**程序**

## 蟒蛇 3

```
import turtle
from turtle import *

setup(500, 500)
Screen()
turtle = turtle.Turtle()
turtle.speed(0)
showturtle()

def up():
    turtle.setheading(90)
    turtle.forward(100)

def down():
    turtle.setheading(270)
    turtle.forward(100)

def left():
    turtle.setheading(180)
    turtle.forward(100)

def right():
    turtle.setheading(0)
    turtle.forward(100)

listen()
onkey(up, 'Up')
onkey(down, 'Down')
onkey(left, 'Left')
onkey(right, 'Right')

mainloop()
```

**输出**

<video class="wp-video-shortcode" id="video-537489-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210106234726/op.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210106234726/op.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210106234726/op.mp4)</video>

### 方法 2:改变颜色

这类似于前面的例子，只是增加了几个键。现在我们添加了改变线条颜色的按键。

*   如果用户按 r，它会变成红色，
*   如果 g 变成绿色，如果 b 变成蓝色。
*   要将线条颜色重置为黑色，用户必须按 z。

此外，通过使用 width()方法将海龟的宽度设置为 5px，可以增加线条的粗细。

**程序**

## 蟒蛇 3

```
import turtle
from turtle import *

setup(500, 500)
Screen()
turtle = turtle.Turtle()
turtle.speed(0)
turtle.width(5)
showturtle()

def up():
    turtle.setheading(90)
    turtle.forward(100)

def down():
    turtle.setheading(270)
    turtle.forward(100)

def left():
    turtle.setheading(180)
    turtle.forward(100)

def right():
    turtle.setheading(0)
    turtle.forward(100)

def r():
    turtle.color("red")

def g():
    turtle.color("green")

def b():
    turtle.color("blue")

def z():
    turtle.color("black")

listen()
onkey(up, 'Up')
onkey(down, 'Down')
onkey(left, 'Left')
onkey(right, 'Right')
onkey(z, "z")
onkey(r, 'r')
onkey(g, 'g')
onkey(b, 'b')

mainloop()
```

**输出**

<video class="wp-video-shortcode" id="video-537489-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210106234927/op.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210106234927/op.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210106234927/op.mp4)</video>