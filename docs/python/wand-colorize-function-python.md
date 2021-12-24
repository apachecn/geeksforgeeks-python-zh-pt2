# 魔杖上色()功能–Python

> 原文:[https://www . geesforgeks . org/wand-colored e-function-python/](https://www.geeksforgeeks.org/wand-colorize-function-python/)

**彩色图像**是指与特定颜色混合的图像。为了生成彩色图像，我们使用 python Wand 中的**彩色化()**功能。**彩色化()**功能将图像与恒定颜色混合。需要两个参数*颜色*和 *alpha* 。

> **语法:**
> 
> ```
> wand.image.colorize(color, alpha)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 颜色 | 魔杖。颜色。颜色 | 用于绘制图像的颜色。 |
> | 希腊字母的第一个字母 | 魔杖。颜色。颜色 | 定义如何混合颜色。 |

**来源影像:**
![](img/8b5bbe4e014c26026f301c16258d80e8.png)

**例 1:**

```
# import Image with wand.image module
from wand.image import Image

# read image using Image() function
with Image(filename ="koala.jpeg") as img:
    # generate colorized image
    img.colorize(color ="yellow", alpha ="rgb(10 %, 0 %, 20 %)")
    img.save(filename ="colorizedkoala.jpeg")
```

**输出:**
![](img/5347fff6be8570d9706ef4384ed29265.png)

**例 2:**
增加α值。

```
from wand.image import Image

# read image using Image() function
with Image(filename ="koala.jpeg") as img:
    # generate colorized image
    img.colorize(color ="yellow", alpha ="rgb(25 %, 0 %, 20 %)")
    img.save(filename ="colorizedkoala2.jpeg")
```

**输出:**
![](img/a3c5de7bfca4ce404c0e511016de29f6.png)