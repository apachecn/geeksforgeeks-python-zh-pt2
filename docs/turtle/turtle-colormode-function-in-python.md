# Python 中的 turtle.colormode()函数

> 原文:[https://www . geesforgeks . org/turtle-color mode-function-in-python/](https://www.geeksforgeeks.org/turtle-colormode-function-in-python/)

海龟模块以面向对象和面向过程的方式提供海龟图形原语。因为它使用 Tkinter 作为底层图形，所以它需要安装一个支持 Tk 的 Python 版本。

## turtle.colormode()

此功能用于返回颜色模式或将其设置为 1.0 或 255。(r，g，b)颜色三元组的值必须在 0 到 c 模式范围内。它只需要一个参数作为值 1.0 或 255 之一的“cmode”。

**语法:**

```
turtle.colormode(mode=None)

```

下面是上述方法的实现，并附有一些例子:

**例 1 :**

## 蟒蛇 3

```
# import package
import turtle

# check the default value
print(turtle.color())
```

**输出:**

```
('black', 'black')

```

**例 2 :**

## 蟒蛇 3

```
# import package
import turtle

# set the colormode to 255
turtle.colormode(255)
# set color
turtle.color(0,0,255)

# motion
for i in range(20):
    turtle.forward(2+2*i)
    turtle.right(90)

# set the colormode to 1.0
turtle.colormode(1.0)

# set color
turtle.color(1.0,0,0)

# motion
for i in range(20):
    turtle.forward(40+4*i)
    turtle.right(90)
```

**输出:**

![](img/620d0f8cd7ae85544749e7dff787476f.png)