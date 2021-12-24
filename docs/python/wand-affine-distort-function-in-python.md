# Python 中的魔杖仿射扭曲()函数

> 原文:[https://www . geeksforgeeks . org/wand-仿射-扭曲-python 中的函数/](https://www.geeksforgeeks.org/wand-affine-distort-function-in-python/)

**仿射**畸变法对图像进行剪切操作。论点类似透视变形法，但只需要一对 3 点 12 实数，方式如下:

```py
src1x, src1y, dst1x, dst1y,
src2x, src2y, dst2x, dst2y,
src3x, src3y, dst3x, dst3y
```

> **语法:**wand . image . transform('仿射'，参数)

**输入图像:**

![](img/a1c18377167bcccc8cbce2b488b9f52a.png)

**示例#1:**

## 蟒蛇 3

```py
# Import Color from wand.color module
from wand.color import Color
# Import Image from wand.image module
from wand.image import Image

with Image(filename ='gog.png') as img:
    img.resize(140, 92)
    img.background_color = Color('skyblue')
    img.virtual_pixel = 'background'
    args = (
        10, 10, 15, 15,  # Point 1: (10, 10) => (15,  15)
        139, 0, 100, 20, # Point 2: (139, 0) => (100, 20)
        0, 92, 50, 80    # Point 3: (0,  92) => (50,  80)
    )
    # affline distortion using distort function
    img.distort('affine', args)
    img.save(filename ="afflinegfg.png")
```

**输出:**

![](img/d37a621370f11a89e66c219f79848831.png)

**示例#2:**
更改参数值。

## 蟒蛇 3

```py
# Import Color from wand.color module
from wand.color import Color
# Import Image from wand.image module
from wand.image import Image

with Image(filename ='gog.png') as img:
    img.resize(140, 92)
    img.background_color = Color('skyblue')
    img.virtual_pixel = 'background'
    args = (
        20, 21, 12, 11,  # Point 1: (10, 10) => (15,  15)
        38, 1, 17, 0, # Point 2: (139, 0) => (100, 20)
        7, 92, 50, 80    # Point 3: (0,  92) => (50,  80)
    )
    # affline distortion using distort function
    img.distort('affine', args)
    img.save(filename ="afflinegfg2.png")
```

**输出:**

![](img/06b395b4e78d22026a7eb72d3e06b209.png)