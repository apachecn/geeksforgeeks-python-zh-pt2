# 如何使用海龟模块在 Python 中绘制 2 层彩色蜘蛛网？

> 原文:[https://www . geeksforgeeks . org/如何绘制 2 层彩色蟒蛇皮蜘蛛网海龟模块/](https://www.geeksforgeeks.org/how-to-draw-2-layered-and-colored-spider-web-in-python-using-turtle-module/)

**先决条件:** [**巨蟒龟模块基础知识**](https://www.geeksforgeeks.org/turtle-programming-python/)

我们一定都在家里看到过蜘蛛网，但是你有没有想过，建造蜘蛛网需要多少努力和耐心。让我们向蜘蛛的努力致敬，继续自己建造一个。蜘蛛网通常由根线和螺旋线组成。如果你能做一个彩色的两层蜘蛛网。这里有一个简单的教程。

**采用的方法:**

海龟被来回移动以首先构建激进的线程。乌龟旋转 60 度来画每根根线。螺旋线的长度设置为 50，每次迭代减少 10。内环涉及构建单个螺旋线和网的分层，而外环控制要构建的螺旋线的数量。

## 蟒蛇 3

```
import turtle as t

# define turtle speed
t.speed(2)

# radical thread 
for i in range(6):
    t.forward(100)
    t.backward(100)
    t.right(60)

# spiral thread length
side = 50

# Spider web color
t.fillcolor("Yellow")

# building web
t.begin_fill()

for i in range(10):
    t.penup()
    t.goto(0, 0)
    t.pendown()
    t.setheading(0)
    t.forward(side)
    t.right(120)

    for j in range(6):
        t.forward(side-2)
        t.right(60)
    side = side - 10

t.end_fill()
```

**输出**

<video class="wp-video-shortcode" id="video-485857-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200915121913/2_layered_spider_web.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200915121913/2_layered_spider_web.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200915121913/2_layered_spider_web.mp4)</video>