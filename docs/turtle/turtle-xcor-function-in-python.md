# Python 中的 turtle.xcor()函数

> 原文:[https://www . geesforgeks . org/turtle-xcor-function-in-python/](https://www.geeksforgeeks.org/turtle-xcor-function-in-python/)

海龟模块以面向对象和面向过程的方式提供海龟图形原语。因为它使用 Tkinter 作为底层图形，所以它需要安装一个支持 Tk 的 Python 版本。

## turtle.xcor()

这个函数用来返回乌龟当前位置的 x 坐标。这不需要任何争论。

**语法:**

```py
turtle.xcor()

```

下面是上述方法的一个示例实现:

**示例:**

## 蟒蛇 3

```py
# import package
import turtle

# check x coordinate
print(turtle.xcor())
turtle.forward(100)

# check x coordinate
print(turtle.xcor())
turtle.right(45)
turtle.forward(100)

# check x coordinate
print(turtle.xcor())
turtle.right(90)
turtle.forward(100)

# check x coordinate
print(turtle.xcor())
turtle.right(45)
turtle.forward(100)

# check x coordinate
print(turtle.xcor())
```

**输出:**

![](img/3117c8f97bf145b99acf39fc3daa9e28.png)

```py
0.0
100.0
170.710678119
100.0
0.0

```