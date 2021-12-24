# Python 中的魔杖路径 _ 水平 _ 线条()函数

> 原文:[https://www . geesforgeks . org/wand-path _ horizontal _ line-python 中的函数/](https://www.geeksforgeeks.org/wand-path_horizontal_line-function-in-python/)

**path_horizontal_line()** 是 path 的另一个函数。函数的作用是:生成一条从目的点到特定 x 点的水平线。它只取参数中的 x 作为一个点，直到哪条线被画出来。

> **语法:**wand . drawing . path _ horizontal _ line(to，relative)
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | x | 真实的 | 要绘制到的 x 轴点。 |
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

    # horizontal line to x=100
    draw.path_horizontal_line(100)
    draw.path_finish()
    with Image(width=200,
               height=200,
               background=Color('lightgreen')) as image:

        draw(image)
        image.save(filename="pathhline.png")
```

**输出:**
![](img/e797f8949a348162a6115bdb47a423f6.png)

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
    draw.path_move(to=(100, 50))

    # horizontal line to x=50
    draw.path_horizontal_line(50)
    draw.path_finish()
    with Image(width=200, 
               height=200,
               background=Color('lightgreen')) as image:

        draw(image)
        image.save(filename="pathhline.png")
```

**输出:**
![](img/a9450b725558dcb47b1ef4a8ecf3bcb6.png)