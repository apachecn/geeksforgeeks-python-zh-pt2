# Python 中的魔杖路径 _ 移动()函数

> 原文:[https://www . geesforgeks . org/wand-path _ move-function-in-python/](https://www.geeksforgeeks.org/wand-path_move-function-in-python/)

**path_move()** 是魔杖中为路径引入的另一个功能。path_move()函数的主要目的是为新的子路径设置新的起点。通过设置相对标志，参数可以是相对的，也可以是绝对的。

> **语法:**
> 
> ```py
> wand.drawing.path_move(to, relative)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 到 | 序列或(数字。真实的数字。真实) | 表示要绘制到的坐标的对。 |
> | 亲戚 | 弯曲件 | 将给定坐标视为相对于当前点。 |

**示例#1:**

```py
from wand.image import Image
from wand.drawing import Drawing
from wand.color import Color

with Drawing() as draw:
    draw.stroke_width = 2
    draw.stroke_color = Color('black')
    draw.fill_color = Color('white')
    draw.path_start()
    # set starting point for first sub-path
    draw.path_move(to =(10, 10))
    # Drawing vertical line from start
    draw.path_vertical_line(100,
                            relative = True)
    # set starting point for second sub-path
    draw.path_move(to =(190, 10))
    # Drawing vertical line from start
    draw.path_vertical_line(100,
                            relative = True)
    draw.path_finish()
    with Image(width = 200, height = 200, background = Color('lightgreen')) as image:
        draw(image)
        image.save(filename ="pathmove.png")
```

**输出:**
![](img/08aa4d644a0f23a62d3479db3b74273e.png)