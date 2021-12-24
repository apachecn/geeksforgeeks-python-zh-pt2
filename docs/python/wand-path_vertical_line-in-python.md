# Python 中的魔杖|路径 _ 竖线()

> 原文:[https://www . geesforgeks . org/wand-path _ vertical _ line-in-python/](https://www.geeksforgeeks.org/wand-path_vertical_line-in-python/)

**path_vertical_line()** 是 path 的另一个函数。path_vertical_line()函数生成一条从目的点到特定 y 点的垂直线。只需要一个点就可以画出一条线。

> **语法:**wand . drawing . path _ vertical _ line(to，relative)
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | y | 真实的 | 要绘制的 y 轴点。 |
> | 亲戚 | 弯曲件 | 将给定坐标视为相对于当前点。 |

**示例#1:**

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
    draw.path_move(to=(10, 50))

    # Line to top-right
    draw.path_vertical_line(100)
    draw.path_finish()
    with Image(width=200,
               height=200, 
               background=Color('lightgreen')) as image:

        draw(image)
        image.save(filename="pathvline.png")
```

**输出:**
![](img/691bfae39996b77d0f3ee0dcde5fffda.png)

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
    draw.path_move(to=(100, 100))

    # Line to top-right
    draw.path_vertical_line(50)
    draw.path_finish()
    with Image(width=200, 
               height=200, 
               background=Color('lightgreen')) as image:

        draw(image)
        image.save(filename="pathvline.png")
```

**输出:**
![](img/439f9004888136e2b692e64ff9da2a44.png)