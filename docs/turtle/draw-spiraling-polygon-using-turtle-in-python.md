# 使用 Python 中的海龟绘制螺旋多边形

> 原文:[https://www . geesforgeks . org/draw-螺旋式-多边形-使用-python 中的海龟/](https://www.geeksforgeeks.org/draw-spiraling-polygon-using-turtle-in-python/)

**先决条件:** [**巨蟒龟基础**](https://www.geeksforgeeks.org/turtle-programming-python/)

**乌龟**是 python 的内置模块。它使我们能够通过海龟、海龟模块中定义的方法以及使用一些逻辑循环来绘制任何图形。要在屏幕(纸板)上画些东西，只需移动乌龟(笔)。移动海龟(笔)有一些功能，如向前()、向后()、等等。

**绘制给定边和尺寸为 n 的螺旋多边形的方法:**

*   导入海龟并创建海龟实例。
*   设置边= 5，多边形的边。
*   用于循环(i = 0 到 i < n *边)并重复以下步骤
    *   海龟.前进(i * 10)。
    *   乌龟。右(360 /边)。
*   关闭海龟实例。

下面是实现:

## 蟒蛇 3

```
# importing turtle module 
import turtle 

# number of side
sides=5

# size
n = 7

# creating instance of turtle 
pen = turtle.Turtle() 

# loop to draw a side 
for i in range(n*sides): 

    # drawing side of 
    # length i*10 
    pen.forward(i * 10) 

    # changing direction of pen 
    # by 360/sides degree in clockwise 
    pen.right(360 / sides)

# closing the instance 
turtle.done() 
```

**输出:**

<video class="wp-video-shortcode" id="video-464052-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200801170003/Polygon.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200801170003/Polygon.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200801170003/Polygon.mp4)</video>