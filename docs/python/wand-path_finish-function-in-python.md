# Python 中的魔杖路径 _finish()函数

> 原文:[https://www . geesforgeks . org/wand-path _ finish-python 中的函数/](https://www.geeksforgeeks.org/wand-path_finish-function-in-python/)

魔杖中路径的另一个重要功能是 **python_finish()** 。当 python_start()启动路径并且终止路径也非常重要时， **path_finish()** 函数处理当前路径的终止。

> **语法:** wand.drawing.path_finish()

**例 1:**

```
from wand.image import Image
from wand.drawing import Drawing
from wand.color import Color

with Drawing() as draw:
    draw.stroke_width = 2
    draw.stroke_color = Color('black')
    draw.path_start()

    # Start middle-left
    draw.path_move(to=(10, 10))
    draw.path_horizontal_line(100)

    # finishes the current path
    draw.path_finish()
    with Image(width=200, 
               height=200,
               background=Color('lightgreen')) as image:
        draw(image)
        image.save(filename = "pathfinish.png")
```

**输出图像:**
![](img/62721b30f02895c1650073b1ab1ba78b.png)

**例 2:**

```
from wand.image import Image
from wand.drawing import Drawing
from wand.color import Color

with Drawing() as draw:
    draw.stroke_width = 2
    draw.stroke_color = Color('black')
    draw.fill_color = Color('white')
    draw.path_start()

    # Start middle-left
    draw.path_move(to=(10, 10))
    draw.path_vertical_line(50)
    draw.path_horizontal_line(50)
    draw.path_vertical_line(100)
    draw.path_horizontal_line(100)

    # finishes the current path
    draw.path_finish()
    with Image(width=200,
               height=200,
               background=Color('lightgreen')) as image:
        draw(image)
        image.save(filename = "pathfinish.png")
```

**输出图像:**
![](img/524f74aa920d625d5afb35e378c1803d.png)