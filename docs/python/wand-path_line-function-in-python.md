# Python 中的 Wand path_line()函数

> 原文:[https://www . geesforgeks . org/wand-path _ line-function-in-python/](https://www.geeksforgeeks.org/wand-path_line-function-in-python/)

**path_line()** 是专门为路径引入的函数。path_line()绘制一条从目的点到我们希望直线结束的点的直线。它只把终点作为论据。

> **语法:**
> 
> ```py
> wand.drawing.path_line(to, relative)
> ```
> 
> **参数:**
> 
> <figure class="table">
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 到 | 序列或(数字。真实的数字。真实) | 表示要绘制到的坐标的对。 |
> | 亲戚 | 弯曲件 | 将给定坐标视为相对于当前点。 |
> 
> </figure>

**示例#1:**

## 蟒蛇 3

```py
from wand.image import Image
from wand.drawing import Drawing
from wand.color import Color

with Drawing() as draw:
    draw.stroke_width = 2
    draw.stroke_color = Color('black')
    draw.fill_color = Color('white')
    draw.path_start()

    # Start middle-left
    draw.path_move(to =(10, 100))

    # Continue path to right
    draw.path_line(to =(100, 0),
                    relative = True)

    # Continue path to bottom left
    draw.path_line(to =(10, 80),
                    relative = True)
    draw.path_finish()
    with Image(width = 200, height = 200, background = Color('lightgreen')) as image:
        draw(image)
        image.save(filename ="pathline.png")
```

**输出:**

![](img/f2443ab2c33ab1085da5d58f080938a2.png)