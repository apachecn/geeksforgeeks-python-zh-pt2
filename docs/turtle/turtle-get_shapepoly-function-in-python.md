# Python 中的 turtle.get_shapepoly()函数

> 原文:[https://www . geesforgeks . org/turtle-get _ shape poly-python 中的函数/](https://www.geeksforgeeks.org/turtle-get_shapepoly-function-in-python/)

海龟模块以面向对象和面向过程的方式提供海龟图形原语。因为它使用 Tkinter 作为底层图形，所以它需要安装一个支持 Tk 的 Python 版本。

## turtle.get_shapepoly()

此方法用于将当前形状多边形作为坐标对的元组返回。这不需要任何争论。

**语法:**

```
turtle.get_shapepoly()

```

下面是上述方法的实现，并附有一些例子:

**例 1 :**

## 蟒蛇 3

```
# import package
import turtle

# get default shape
print(turtle.shape())

# get default shapeploy
print(turtle.get_shapepoly())

# set some size
turtle.turtlesize(5, 5, 2)

# get default shapeploy
print(turtle.get_shapepoly())
```

**输出:**

```
classic
((0, 0), (-5, -9), (0, -7), (5, -9))
((0.0, 0.0), (-25.0, -45.0), (0.0, -35.0), (25.0, -45.0))

```

**例 2 :**

## 蟒蛇 3

```
# import package
import turtle

# get all shapes
shp=turtle.getshapes()
print(shp)

# loop for getting shapepoly
# of all the shapes
for i in range(len(shp)):
    turtle.shape(shp[i])
    print(turtle.get_shapepoly())
```

**输出:**

> ['箭头'，'空白'，'圆形'，'经典'，'正方形'，'三角形'，'乌龟']
> ((-10，0)，(0，10))
> 无
> ((10，0)，(9.51，3.09)，(8.09，5.88)，(5.88，8.09)，(3.09，9.51)，(0，10)，(-3.09，9.51)，(-5.88，8.09)，
> (-1) 11.55)、(-10，-5.77))
> ((0，16)、(-2，14)、(-1，10)、(-4，7)、(-7，9)、(-9，8)、(-6，5)、(-7，1)、(-5，-3)、(-8，-6)、(-6，-8)、
> (-4，-5)、(0，-7)、(4，-5)、(6，-8)、(8，-6)、(5，-3)、(7，1)、(6，5)