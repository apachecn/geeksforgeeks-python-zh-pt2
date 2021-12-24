# Python 中的 turtle.get_poly()函数

> 原文:[https://www . geesforgeks . org/turtle-get _ poly-function-in-python/](https://www.geeksforgeeks.org/turtle-get_poly-function-in-python/)

海龟模块以面向对象和面向过程的方式提供海龟图形原语。因为它使用 Tkinter 作为底层图形，所以它需要安装一个支持 Tk 的 Python 版本。

## turtle.get_poly()

该函数用于返回最后记录的多边形。这不需要任何争论。

**语法:**

```
turtle.get_poly()

```

下面是上述方法的一个示例实现:

**示例:**制作一个多边形，使用 get_poly()方法

在本例中，我们绘制了一个[椭圆](https://www.geeksforgeeks.org/draw-ellipse-using-turtle-in-python/)并用 begin_poly()和 end_poly()方法记录下来。通过 get_poly()方法，我们可以得到多边形的所有坐标，然后打印出来。我们也可以用它来记录形状。

## 蟒蛇 3

```
# import package
import turtle

# start recording polygon
turtle.begin_poly()

# form an ellipse
turtle.circle(20,90) 
turtle.circle(10,90)
turtle.circle(20,90) 
turtle.circle(10,90)

# end recording polygon
turtle.end_poly()

# get poly that recorded
print(turtle.get_poly())
```

**输出:**

<video class="wp-video-shortcode" id="video-460317-1" width="665" height="374" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200727202543/turtle-python.webm?_=1">[https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200727202543/turtle-python.webm](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200727202543/turtle-python.webm)</video>

> ((0.00，0.00)，(7.65，1.52)，(14.14，5.86)，(18.48，12.35)，(20.00，20.00)，(19.24，23.83)，(17.07，27.07)，
> (13.83，29.24)，(10.00，30.00)，(2.35，28.48)，(-4.14