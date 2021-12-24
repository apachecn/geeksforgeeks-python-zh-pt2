# 用乌龟用 Python 画圆

> 原文:[https://www . geesforgeks . org/draw-circle-in-python-use-turtle/](https://www.geeksforgeeks.org/draw-circle-in-python-using-turtle/)

乌龟是 Python 的一个功能，就像画板一样，让我们命令一只乌龟在上面画来画去！我们可以使用像 turtle.forward(…)和 turtle.right(…)这样的函数来移动乌龟。海龟是一种初学者友好的学习 Python 的方法，通过运行一些基本命令并查看海龟的图形来完成。它就像一个画板，可以让你在上面画画。海龟模块可以以面向对象和面向过程的方式使用。
画图，Python 龟提供了很多功能和方法，即前进、后退等。一些常用的方法有:

*   **向前(x):** 向前移动笔 x 个单位。
*   **向后(x):** 将笔向后移动 x 个单位。
*   **右(x):** 顺时针方向旋转笔 x 角度。
*   **左(x):** 逆时针方向旋转笔 x 角度。
*   **penip():**停止龟笔的绘制。
*   **pendown():** 开始画龟笔。

现在用龟画一个圆，我们将使用“龟”中的一个预定义函数。
**圆(半径):**这个函数以“龟”的位置为中心，画一个给定半径的圆。
**例:**

## 蟒蛇 3

```
# Python program to demonstrate
# circle drawing

import turtle

# Initializing the turtle
t = turtle.Turtle()

r = 50
t.circle(r)
```