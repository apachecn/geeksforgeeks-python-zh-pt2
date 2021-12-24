# Python 中的 turtle.towards()函数

> 原文:[https://www . geesforgeks . org/turtle-to-function-in-python/](https://www.geeksforgeeks.org/turtle-towards-function-in-python/)

海龟模块以面向对象和面向过程的方式提供海龟图形原语。因为它使用 tkinter 作为底层图形，所以需要安装一个支持 Tk 的 Python 版本。

## 海龟.朝向()

该函数用于返回从海龟位置到 x，y 指定位置的直线与海龟起始方向之间的角度。

**语法:**

```
turtle.towards(x, y=None)

```

**参数:**

<figure class="table">

| **论据** | **描述** |
| x | 数字或数字对/向量或海龟实例 |
| y | 数字或无或无 |

</figure>

下面用一个例子来说明上述方法的实现:

## python 3

```
# import package
import turtle

# go towards east
ang=turtle.towards(100,0)

# print angle
print(ang)

# go towards north
ang=turtle.towards(0,100)

# print angle
print(ang)

# go towards west
ang=turtle.towards(-100,0)

# print angle
print(ang)

# go towards south
ang=turtle.towards(0,-100)

# print angle
print(ang)
```

**输出:**

```
0.0
90.0
180.0
270.0

```

这里我们可以看到，一个人可以很容易地得到一个指向任何坐标点的角度，而不用去那个点。在上面的例子中，海龟保持在(0，0)上，也就是说，在没有任何移动的情况下，回到指定的位置。