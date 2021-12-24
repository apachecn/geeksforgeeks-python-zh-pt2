# 蟒蛇龟圈彩花

> 原文:[https://www . geesforgeks . org/彩色圈花-使用蟒蛇皮乌龟/](https://www.geeksforgeeks.org/colored-flower-by-circles-using-turtle-in-python/)

#### 先决条件: [<u>海龟编程基础知识</u>T5】](https://www.geeksforgeeks.org/turtle-programming-python/)

**海龟**是 Python 中的内置模块。它提供使用屏幕(纸板)和乌龟(钢笔)的绘图。要在屏幕上画东西，我们需要移动乌龟(笔)。要移动海龟，有一些功能，例如向前()，向后()，等等。

#### 要绘制花:

> 使用以下步骤:
> 
> *   进口海龟
> *   设置屏幕
> *   制作海龟对象
> *   定义用于绘图的颜色
> *   循环绘制按角度定向的圆。

下面是实现:

## 蟒蛇 3

```
# import turtle package 
import turtle

# screen object
sc = turtle.Screen()   

# turtle object
pen = turtle.Turtle()  

# Driver Code
# colors
col = ['violet', 'indigo', 'blue', 'green', 
       'yellow', 'orange', 'red']

# screen size
sc.setup(500,500) 

# screen color
sc.bgcolor('black')

# turtle size
pen.pensize(4) 

# turtle object
pen.speed(20)    

# integer variable 
# for accessing colors
i = 0

# loop to draw 30 circles 
for angle in range(0, 360, 12):

  # color of circle
  pen.color(col[i])  

  if i == 6:           
    i = 0

  else:
    i += 1

  # Set the orientation of
  # the turtle to angle
  pen.seth(angle) 

  # circle of radius 80
  pen.circle(80) 

# hide the turtle
pen.ht()
```

#### 输出:

![Coloured flower by circle](img/a315495559a977d05e47e7417ce96ac2.png)