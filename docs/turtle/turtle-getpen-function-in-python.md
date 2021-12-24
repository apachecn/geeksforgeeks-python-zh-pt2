# Python 中的 turtle.getpen()函数

> 原文:[https://www . geesforgeks . org/turtle-getpen-function-in-python/](https://www.geeksforgeeks.org/turtle-getpen-function-in-python/)

海龟模块以面向对象和面向过程的方式提供海龟图形原语。因为它使用 Tkinter 作为底层图形，所以它需要安装一个支持 Tk 的 Python 版本。

## turtle.getpen()

该函数用于返回 Turtleobject 本身。这不需要任何争论。

**语法:**

```py
turtle.getpen()

```

下面是上述方法的实现，并附有一些例子:

**例 1 :**

## 蟒蛇 3

```py
# import package
import turtle

# get turtle object
# and store it 
turt=turtle.getpen()

# print turtle object
print(turt)
```

**输出:**

```py
<__main__.Turtle object>

```

**例 2 :**

## 蟒蛇 3

```py
# import package
import turtle

# get turtle object
# and store it 
turt=turtle.getpen()

# use it for turtle methods
turt.width(5)
turt.color("blue")
turt.shape("turtle")
turt.forward(150)
```

**输出:**

![](img/86bcd5400bf84b964fd6c5076d7bac09.png)