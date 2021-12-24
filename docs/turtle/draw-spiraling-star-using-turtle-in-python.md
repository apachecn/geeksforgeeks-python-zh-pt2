# 使用 Python 中的海龟绘制螺旋星

> 原文:[https://www . geeksforgeeks . org/draw-spiral-star-use-turtle-in-python/](https://www.geeksforgeeks.org/draw-spiraling-star-using-turtle-in-python/)

#### **先决条件:** [蟒蛇龟基础知识](https://www.geeksforgeeks.org/turtle-programming-python/)

**乌龟**是 python 的内置模块。它使我们能够通过海龟和海龟模块中定义的方法以及使用一些逻辑循环来绘制任何图形。要在屏幕(纸板)上画些东西，只需移动乌龟(笔)。要移动乌龟(笔)有一些功能，即*向前()，向后()，*等
**方法绘制一个 n 大小的螺旋星:**

*   导入海龟并创建海龟实例。
*   用于循环(i=0 至 i
    *   海龟.前进(i*10)
    *   乌龟.右(144)
*   关闭海龟实例。

## 蟒蛇 3

```
# importing turtle module
import turtle

# number of sides
n = 10

# creating instance of turtle
pen = turtle.Turtle()

# loop to draw a side
for i in range(n):
    # drawing side of 
    # length i*10
    pen.forward(i * 10)

    # changing direction of pen 
    # by 144 degree in clockwise
    pen.right(144)

# closing the instance
turtle.done()
```

**输出:**

<video class="wp-video-shortcode" id="video-445601-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200701074648/video5.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200701074648/video5.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200701074648/video5.mp4)</video>