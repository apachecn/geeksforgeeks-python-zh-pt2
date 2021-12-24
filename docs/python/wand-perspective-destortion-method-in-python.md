# Python 中的魔杖透视变形方法

> 原文:[https://www . geesforgeks . org/wand-perspective-destortion-method-in-python/](https://www.geeksforgeeks.org/wand-perspective-destortion-method-in-python/)

**透视**是扭曲函数中的另一种扭曲方法。它代表基于参数的透视图像。透视扭曲需要 4 对点，总共是 16 对。参数的顺序是成组的源&目标坐标对。

```py
src1x, src1y, dst1x, dst1y,
src2x, src2y, dst2x, dst2y,
src3x, src3y, dst3x, dst3y,
src4x, src4y, dst4x, dst4y
```

**语法:**

```py
wand.image.distort('perspective', arguments')
```

**来源图片:**

![](img/a1c18377167bcccc8cbce2b488b9f52a.png)

**示例#1:**

## 蟒蛇 3

```py
# Import Color from wand.color module
from wand.color import Color
# Import Image from wand.image module
from wand.image import Image

with Image(filename ='gog.png') as img:
    img.virtual_pixel = 'background'
    img.background_color = Color('green')
    img.matte_color = Color('skyblue')
    arguments = (0, 0, 20, 60,
                 90, 0, 70, 63,
                 0, 90, 5, 83,
                 90, 90, 85, 88)
    # perspective distortion using distort function
    img.distort('perspective', arguments)
    img.save(filename ='gfg_p.png')
```

**输出:**

![](img/0fd8461c314356255ae7e85526d5f185.png)

**示例#2:** 使用 itertools 链
分割源点和目的点

## 蟒蛇 3

```py
from itertools import chain
# Import Color from wand.color module
from wand.color import Color
# Import Image from wand.image module
from wand.image import Image

with Image(filename ='gog.png') as img:
    img.background_color = Color('skyblue')
    img.virtual_pixel = 'background'
    sp = (
        (0, 0),
        (140, 0),
        (0, 92),
        (140, 92)
    )
    dp = (
        (14, 4.6),
        (126.9, 9.2),
        (0, 92),
        (140, 92)
    )
    order = chain.from_iterable(zip(sp, dp))
    arguments = list(chain.from_iterable(order))
    img.distort('perspective', arguments)
    img.save(filename ='gfg_p2.png')
```

**输出:**

![](img/9d3c14bb959857870c8da6ad52e43ad2.png)