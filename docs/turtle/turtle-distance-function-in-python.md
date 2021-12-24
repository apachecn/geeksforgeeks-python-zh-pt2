# Python 中的 turtle.distance()函数

> 原文:[https://www . geesforgeks . org/turtle-distance-function-in-python/](https://www.geeksforgeeks.org/turtle-distance-function-in-python/)

海龟模块以面向对象和面向过程的方式提供海龟图形原语。因为它使用 tkinter 作为底层图形，所以需要安装一个支持 Tk 的 Python 版本。

## 海龟.距离()

此方法用于以龟步为单位返回龟到(x，y)的距离。

> **语法:**海龟.距离(x，y =无)
> 
> **参数:**
> 
> **x:** 矢量 2DVec 的 x 坐标。
> 
> **y:** 矢量 2DVec 的 y 坐标。

这个方法可以用不同的格式调用，如下所示:

```
distance(x, y) # two coordinates

distance((x, y)) # a pair (tuple) of coordinates

distance(vec) # e.g. as returned by pos()

distance(mypen) # where mypen is another turtle
```

下面是上述方法的实现，并附有一些例子:

**例 1 :**

## 蟒蛇 3

```
# importing package
import turtle

# print the distance
# before any motion
print(turtle.distance())

# forward turtle by 100
turtle.forward(100)

# print the distance
# after a motion
print(turtle.distance())
```

**输出:**

```
0.0
100.0
```

**例 2 :**

## 蟒蛇 3

```
# importing package
import turtle

# print distance (default)
print(turtle.distance())

for i in range(4):

    # draw one quadrant
    turtle.circle(50,90)

    # print distance
    print(turtle.distance())
```

**输出:**

```
0.0
70.7106781187
100.0
70.7106781187
1.41063873243e-14 
```

**例 3:**

## 蟒蛇 3

```
# importing package
import turtle

# print distance with arguments
# in different formats
print(turtle.distance(3,4))
print(turtle.distance((3,4)))
print(turtle.distance((30.0,40.0)))
```

**输出:**

```
5.0
5.0
50.0
```