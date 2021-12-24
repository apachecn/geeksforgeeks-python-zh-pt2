# 使用 Python 中的海龟绘制螺旋三角形

> 原文:[https://www . geesforgeks . org/draw-螺旋式-三角形-使用-python 中的海龟/](https://www.geeksforgeeks.org/draw-spiraling-triangle-using-turtle-in-python/)

**先决条件:** [**巨蟒龟基础**](https://www.geeksforgeeks.org/turtle-programming-python/)

**乌龟**是 python 的内置模块。它使我们能够通过海龟、海龟模块中定义的方法以及使用一些逻辑循环来绘制任何图形。要在屏幕(纸板)上画些东西，只需移动乌龟(笔)。移动海龟(笔)有一些功能，如向前()、向后()、等等。

**绘制 n 尺寸螺旋三角形的方法:**

*   导入海龟并创建海龟实例。
*   用于循环(i = 0 至 i< n * 3)并重复以下步骤
    *   海龟.前进(i * 10)。
    *   乌龟。对(120)。
*   关闭海龟实例。

下面是实现:

## 蟒蛇 3

```py
# importing turtle module 
import turtle 

# size
n = 10

# creating instance of turtle 
pen = turtle.Turtle() 

# loop to draw a side 
for i in range(n * 3): 

    # drawing side of 
    # length i*10 
    pen.forward(i * 10) 

    # changing direction of pen 
    # by 120 degree in clockwise 
    pen.right(120)

# closing the instance 
turtle.done() 
```

**输出:**

<video class="wp-video-shortcode" id="video-464079-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200801164808/triangle.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200801164808/triangle.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200801164808/triangle.mp4)</video>