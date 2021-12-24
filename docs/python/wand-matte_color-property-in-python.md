# Python 中的魔杖哑光 _ 颜色属性

> 原文:[https://www . geesforgeks . org/wand-matt _ color-property-in-python/](https://www.geeksforgeeks.org/wand-matte_color-property-in-python/)

有些失真过渡无法在虚拟像素空间中计算。要么无效，要么 NaN(不是数字)。您可以通过设置 Image.matte _ color 属性来定义如何表示这样的像素。

**语法:**

```
wand.image.matte_color = 'color'

```

**来源影像:**
![](img/90bb37e50c66f2f6d39a81ac08643202.png)

**Example 1:**

```
from wand.color import Color
# Import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="gog.png") as img:
    img.matte_color = Color('BLUE')
    img.virtual_pixel = 'tile'  
    args = (0, 0, 30, 60, 140, 0, 110, 60,
            0, 92, 2, 90, 140, 92, 138, 90)
    img.distort('perspective', args)
    img.save(filename ="rdmc.jpg")
```

**输出:**
![](img/9603c48a5aa881c6dbe156a08e3b4d3c.png)

**示例 2:**
将 VIRTUAL_PIXEL_METHOD 更改为 tile

```
from wand.color import Color
# Import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="gog.png") as img:
    arguments = (0, 0, 20, 60,
                 90, 0, 70, 63,
                 0, 90, 5, 83,
                 90, 90, 85, 88)
    img.matte_color = Color('YELLOW')
    img.distort('perspective', arguments)
    img.save(filename ='mattegog.png')
```

**输出:**
![](img/a14cece80645c3c4cfeed2ba8ee6a66f.png)