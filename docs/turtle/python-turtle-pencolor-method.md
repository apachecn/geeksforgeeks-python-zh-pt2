# 蟒蛇–甲鱼()方法

> 原文:[https://www . geesforgeks . org/python-turtle-pencolor-method/](https://www.geeksforgeeks.org/python-turtle-pencolor-method/)

[海龟](https://www.geeksforgeeks.org/turtle-programming-python/)模块以面向对象和面向过程的方式提供海龟图形原语。因为它使用 [tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/) 作为底层图形，所以它需要一个安装了 Tk 支持的 Python 版本。

## turtle.pencolor():

这个方法是用来改变龟画的墨水颜色的。默认颜色是黑色。

> **语法:** turtle.pencolor(*args)
> 
> **参数:**该方法有以下参数:
> 
> *   **颜色串:**(可选)颜色串一串颜色名称，如“红”、“绿”等。
> *   **(r，g，b):** (可选)使用 rgb 颜色代码的三个值 r，g 和 b 的元组。
> *   **r、g、b:** (可选)使用 rgb 色码的三个值 r、g 和 b。
> 
> **返回:**无

下面是上述方法的一个实现示例:

## 蟒蛇 3

```py
# importing turtle package
import turtle

# set turtle shape
turtle.shape("turtle")

# set the colormode
turtle.colormode(255)

# use forward by 100 pixel
# default pen color is  black
turtle.forward(100)

# change the pencolor
# pencolor is red
turtle.pencolor("red")

# use forward by 100 pixel
# then 90 degrees right
turtle.right(90)
turtle.forward(100)

# change the pencolor
# pencolor is blue
turtle.pencolor((41,41,253))

# use forward by 100 pixel
# then 90 degrees right
turtle.right(90)
turtle.forward(100)

# change the pencolor
# pencolor is green
turtle.pencolor(41,253,41)

# use forward by 100 pixel
# then 90 degrees right
turtle.right(90)
turtle.forward(100)

# This code is contributed
# by Deepanshu Rustagi.
```

**输出:**

![Output turtle pencolor changes demo](img/bb93394a2565175535f08b12d3952fbc.png)