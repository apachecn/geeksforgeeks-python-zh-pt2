# Python 中的 turtle.window_height()函数

> 原文:[https://www . geesforgeks . org/turtle-window _ height-function-in-python/](https://www.geeksforgeeks.org/turtle-window_height-function-in-python/)

海龟模块以面向对象和面向过程的方式提供海龟图形原语。因为它使用 Tkinter 作为底层图形，所以它需要安装一个支持 Tk 的 Python 版本。

## turtle.window_height()

这个函数用来返回龟窗的高度。这不需要任何争论。

**语法:**

```py
turtle.window_height()

```

下面是上述方法的一个示例实现:

## 蟒蛇 3

```py
# import package
import turtle

# get turtle window height
print(turtle.window_height())

# make screen object
# then set size and color
sc = turtle.Screen()
sc.setup(300,300)
sc.bgcolor("green")

# get turtle window height
print(turtle.window_height())

# loops for pass time
for i in range(5000):
  for j in range(5000):
    pass

# set size and color again
sc.setup(500,400)
sc.bgcolor("red")

# get turtle window height
print(turtle.window_height())
```

**输出:**

![](img/71612d5717684ef1b8214e989a03fdad.png)

```py
648
300
400

```