# 用 Python 中的乌龟用 VIBGYOR 画同心圆

> 原文:[https://www . geeksforgeeks . org/draw-同心圆-with-vib gyor-using-海龟-in-python/](https://www.geeksforgeeks.org/draw-concentric-circles-with-vibgyor-using-turtle-in-python/)

#### 先决条件: [<u>海龟编程基础知识</u>](https://www.geeksforgeeks.org/turtle-programming-python/)

**海龟**是 Python 中的内置模块。它提供使用屏幕(纸板)和乌龟(钢笔)的绘图。要在屏幕上画东西，我们需要移动乌龟(笔)。要移动海龟，有一些功能，例如向前()，向后()，等等。

#### 要绘制同心振动:

> 使用以下步骤:
> 
> *   导入海龟模块
> *   设置屏幕
> *   制作海龟对象
> *   用动态半径和颜色定义圆的方法。
> *   通过在所需位置设置海龟对象来编写文本。

下面是实现:

## 蟒蛇 3

```py
# import turtle package
import turtle

# Screen object
sc = turtle.Screen()

# Screen background color
sc.bgcolor('black')

# turtle object
pen = turtle.Turtle()

# turtle width
pen.width(4)

# function to draw a circle of
# rad radius and col color
def circle(col, rad, val):

    pen.color(col)
    pen.circle(rad)
    pen.up()

    # set position for space
    pen.setpos(0, val)
    pen.down()

# function to write text
# by setting positions
def text():

    pen.color('white')
    pen.up()
    pen.setpos(-100, 140)
    pen.down()
    pen.write("Concentric VIBGYOR",
              font = ("Verdana", 15))
    pen.up()
    pen.setpos(-82, -188)
    pen.down()
    pen.write("Using Turtle Graphics",
              font = ("Verdana", 12))
    pen.hideturtle()

# Driver code

if __name__ == "__main__" :

  # VIBGYOR color list
    col = ['violet', 'indigo', 'blue',
         'green', 'yellow', 'orange',
         'red']

  # 7 Concentric circles
  for i in range(7):

      # function call
      circle(col[i], -20*(i+1), 20*(i+1))

  # function call
  text()
```

#### 输出:

![](img/3cbdd9d7c9785868ac46e296f8ffc430.png)

同心振动仪