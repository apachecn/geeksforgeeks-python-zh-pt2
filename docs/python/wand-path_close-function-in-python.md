# Python 中的魔杖路径 _close()函数

> 原文:[https://www . geesforgeks . org/wand-path _ close-function-in-python/](https://www.geeksforgeeks.org/wand-path_close-function-in-python/)

**path_move()** 是路径魔杖中包含的另一个功能。该函数的主要目的是将路径中的最后一个目的点连接到第一个点。它只是向当前路径添加一个 path 元素，通过从当前点到当前子路径最近的起点画一条直线来关闭当前子路径。

> **语法:** draw.path_close()
> **参数:**此函数无参数。

**代码:**

## 蟒蛇 3

```
# importing wand
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
    # Curve across top-left to center
    draw.path_curve(to =(80, 0),
                    controls =[(20, -80), (60, -80)],
                    relative = True)
    # Continue curve across bottom-right
    draw.path_curve(to =(80, 0),
                    controls =(60, 80),
                    smooth = True,
                    relative = True)
    # Join the last destination point to the first point
    draw.path_close()
    draw.path_finish()
    with Image(width = 200, height = 200, background = Color('lightgreen')) as image:
        draw(image)
        image.save(filename = "pathclose.png")
```

**输出:**

![](img/2f3230b4ec4990dd9c45140310c597f9.png)