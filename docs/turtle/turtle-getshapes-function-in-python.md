# Python 中的 turtle.getshapes()函数

> 原文:[https://www . geesforgeks . org/turtle-getshapes-function-in-python/](https://www.geeksforgeeks.org/turtle-getshapes-function-in-python/)

海龟模块以面向对象和面向过程的方式提供海龟图形原语。因为它使用 Tkinter 作为底层图形，所以它需要安装一个支持 Tk 的 Python 版本。

## turtle.getshapes()

该函数用于返回所有当前可用海龟形状的名称列表。这不需要任何争论。

**语法:**

```py
turtle.getshapes()

```

下面是上述方法的实现，并附有一些例子:

**例 1 :**

## 蟒蛇 3

```py
# import package
import turtle
print(turtle.getshapes())
```

**输出:**

```py
['arrow', 'blank', 'circle', 'classic', 'square', 'triangle', 'turtle']

```

**例 2 :**

## 蟒蛇 3

```py
# import package
import turtle
shapes = turtle.getshapes()

# set speed to slowest
turtle.speed(1)

# draw all shapes
for i in range(len(shapes)):

  # shape
  turtle.shape(shapes[i])

  # motion
  turtle.forward(100)
  turtle.right(51.42)
  turtle.stamp()
```

**输出:**

![](img/0d8dda7fa552ed267d64fe4e1ddc7516.png)