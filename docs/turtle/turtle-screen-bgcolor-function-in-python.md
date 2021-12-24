# 甲鱼。屏幕()。Python 中的 bgcolor()函数

> 原文:[https://www . geesforgeks . org/turtle-screen-bgcolor-function-in-python/](https://www.geeksforgeeks.org/turtle-screen-bgcolor-function-in-python/)

海龟模块以面向对象和面向过程的方式提供海龟图形原语。因为它使用 Tkinter 作为底层图形，所以它需要安装一个支持 Tk 的 Python 版本。

## 乌龟。屏幕()。bgcolor()

此方法用于设置或返回龟屏的背景色。

**语法:**

```
turtle.bgcolor(*args)

```

**参数:**

<figure class="table">

| **格式** | **参数** | **描述** |
| --- | --- | --- |
| bgcolor(颜色) | 颜色 | 颜色名称字符串 |
| bgcolor(r、g、b) | r、g、b | rgb 颜色代码值 |

</figure>

下面是上述方法的实现，并附有一些例子:

**例 1 :**

## 蟒蛇 3

```
# importing package
import turtle

# set the background color
# of the turtle screen
turtle.Screen().bgcolor("orange")

# move turtle
turtle.forward(100)
```

**输出:**

![](img/58f1bc4ea7391ba291e2f0ea7564fc52.png)

**例 2 :**

## 蟒蛇 3

```
# importing package
import turtle

# set the background color
# of the turtle screen
turtle.Screen().bgcolor(0,0,255)

# move turtle
turtle.forward(100)
```

**输出:**

![](img/1330398abf984c8cd0dcc9e8b7366226.png)