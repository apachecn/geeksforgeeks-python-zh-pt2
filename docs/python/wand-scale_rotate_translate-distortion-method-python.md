# 魔杖缩放 _ 旋转 _ 平移变形方法 Python

> 原文:[https://www . geesforgeks . org/wand-scale _ rotate _ translate-distortion-method-python/](https://www.geeksforgeeks.org/wand-scale_rotate_translate-distortion-method-python/)

一种更常见的失真方法是 scale_rotate_translate。大量参数由 scale_rotate_translate 方法控制。由 scale_rotate_translate 方法控制的参数如下:

*   X
*   Y
*   ScaleX
*   ScaleY
*   角
*   纽克斯
*   新的

> **语法:**base image . translate(' scale _ rotate _ translate '，**kwargs)

**输入图像:**
![](img/a1c18377167bcccc8cbce2b488b9f52a.png)

**示例#1:**

```py
# Import Color from wand.color module
from wand.color import Color
# Import Image from wand.image module
from wand.image import Image

with Image(filename ='gog.png') as img:
    img.resize(140, 92)
    img.background_color = Color('skyblue')
    img.virtual_pixel = 'background'
    angle = 90.0

    # scale_rotate_translate method using distort function
    img.distort('scale_rotate_translate', (angle, ))
    img.save(filename ="srtgfg.png")
```

**输出:**
![](img/78542aa9cfb6adbf15008027400bde54.png)

**例 2:**

```py
# Import Color from wand.color module
from wand.color import Color
# Import Image from wand.image module
from wand.image import Image

with Image(filename ='gog.png') as img:
    img.resize(140, 92)
    img.background_color = Color('skyblue')
    img.virtual_pixel = 'background'
    angle = 90.0
    scale = 0.5

    # scale_rotate_translate method using distort function
    img.distort('scale_rotate_translate', (scale, angle, ))
    img.save(filename ="srtgfg2.png")
```

**输出:**
![](img/df19bb12c94ba1e8c00ae65a803a2c44.png)