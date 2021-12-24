# Python 中的魔杖折线()函数

> 原文:[https://www . geesforgeks . org/wand-polyline-function-in-python/](https://www.geeksforgeeks.org/wand-polyline-function-in-python/)

**折线()**是魔杖绘图模块中的另一个绘图功能。折线()类似于多边形()函数唯一的区别是，它不会关闭笔画线 b/w 的第一点和最后一点。与 polygon()类似，它也以点元组列表作为参数。

> **语法:**
> 
> ```
> wand.drawing.polyline(points)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 点 | 目录 | x，y 元组列表。 |

**示例#1**

```
from wand.image import Image
from wand.drawing import Drawing
from wand.color import Color

with Drawing() as draw:
    draw.stroke_width = 2
    draw.stroke_color = Color('black')
    draw.fill_color = Color('white')

    # points list for polygon
    points = [(25, 25), (175, 100), (25, 175)]

    # draw polygon using polygon() function
    draw.polyline(points)
    with Image(width = 200, height = 200, background = Color('lightgreen')) as image:
        draw(image)
        image.save(filename = "polygon.png")
```

**输出:**
![](img/5051184851c5f9526de5bbb45ca5ffbd.png)

**例 2:**

```
from wand.image import Image
from wand.drawing import Drawing
from wand.color import Color

with Drawing() as draw:
    draw.stroke_width = 2
    draw.stroke_color = Color('black')
    draw.fill_color = Color('white')

    # points list for polygon
    points = [(25, 150), (50, 50), (150, 50), (175, 150)]

    # draw polygon using polygon() function
    draw.polyline(points)
    with Image(width = 200, height = 200, background = Color('lightgreen')) as image:
        draw(image)
        image.save(filename = "polyline2.png")
```

**输出:**
![](img/6f25c8c1a969b1477b41c7b39449ba1d.png)