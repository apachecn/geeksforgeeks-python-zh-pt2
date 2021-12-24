# 如何在 Python 中创建自定义的海龟形状？

> 原文:[https://www . geeksforgeeks . org/如何在 python 中创建自定义海龟形状/](https://www.geeksforgeeks.org/how-to-create-custom-turtle-shapes-in-python/)

在海龟中，默认情况下，我们有一个箭头形状的光标在画布上绘制。这可以更改为一些其他预定义的形状，或者我们也可以创建一个自定义形状并将其注册在一个名称下。不仅如此，我们甚至可以使用 *gif* 格式的图像来代替我们的光标。

## 将光标更改为预定义的形状

**形状()**功能用于设置光标的形状。预定义的形状包括*龟*、*箭*、*圆*、*方*和*三角*。

## 蟒蛇 3

```py
import turtle

# turtle object
c_turtle = turtle.Turtle()

# changing the cursor
# shape to circle
c_turtle.shape('circle')
```