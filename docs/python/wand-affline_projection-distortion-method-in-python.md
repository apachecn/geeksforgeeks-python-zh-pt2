# Python 中的魔杖阿弗莱恩 _ 投影变形法

> 原文:[https://www . geesforgeks . org/wand-a fline _ projection-transformation-in-method-python/](https://www.geeksforgeeks.org/wand-affline_projection-distortion-method-in-python/)

**阿弗莱恩投影**非常类似于 scale_rotate_translate 扭曲类型。唯一不同的是，它需要六个实数作为失真参数。

```py
Scalex, Rotatex, Rotatey, Scaley, Translatex, Translatey

```

**来源影像:**
![](img/a1c18377167bcccc8cbce2b488b9f52a.png)

**Example #1:**

```py
from collections import namedtuple
# Import Color from wand.color module
from wand.color import Color
# Import Image from wand.image module
from wand.image import Image

Point = namedtuple('Point', ['x', 'y'])

with Image(filename ='gog.png') as img:
    img.background_color = Color('skyblue')
    img.virtual_pixel = 'background'
    rotate = Point(0.1, 0)
    scale = Point(0.7, 0.6)
    translate = Point(5, 5)
    args = (
        scale.x, rotate.x, rotate.y,
        scale.y, translate.x, translate.y
    )
    img.distort('affine_projection', args)
    img.save(filename ="afflinegfg.png")
```

**输出:**
![](img/18417edf5abce7619e8fde41986efb3e.png)

**示例#2:**
更改参数值。

```py
# Import Color from wand.color module
from wand.color import Color
# Import Image from wand.image module
from wand.image import Image

with Image(filename ='gog.png') as img:
    img.background_color = Color('skyblue')
    img.virtual_pixel = 'background'
    rotate = Point(0.1, 0.3)
    scale = Point(0.9, 0.2)
    translate = Point(7, 5)
    args = (
        scale.x, rotate.x, rotate.y,
        scale.y, translate.x, translate.y
    )
    img.distort('affine_projection', args)
    img.save(filename ="afflinegfg2.png")
```

**输出:**
![](img/e6a3e7ef8be612e864c149414f351402.png)