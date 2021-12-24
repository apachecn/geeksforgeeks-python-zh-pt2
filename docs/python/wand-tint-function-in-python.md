# Python 中的魔杖着色()功能

> 原文:[https://www.geeksforgeeks.org/wand-tint-function-in-python/](https://www.geeksforgeeks.org/wand-tint-function-in-python/)

**tint()** 函数通过混合给定的颜色为图像的中间色调着色。alpha 参数控制颜色通道之间混合的效果。然而，这可能很难使用，所以当有疑问时，使用 alpha="gray(50)"参数。

> **语法:**
> 
> ```py
> wand.image.tint(color, alpha)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 颜色 | 颜色 | 计算中间色调的颜色。
>  |
> | 希腊字母的第一个字母 | 颜色 | 确定如何混合。
>  |

**来源影像:**
![](img/a1d5dabac07efe8de363e0c440a198d8.png)

**例 1:**

```py
# Import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="koala.jpeg") as img:

    # tinted image using tint() function
    img.tint(color ="yellow", alpha ="rgb(40 %, 60 %, 80 %)")
    img.save(filename ="tintkoala.jpeg")
```

**输出:**
![](img/b2cdc1506413a74a86295492c10a7a29.png)

**例 2:** 增加金额值

```py
# Import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="koala.jpeg") as img:

    # implode imagefx using implode() function
    img.tint(color ="green", alpha ="rgb(10 %, 20 %, 40 %)")
    img.save(filename ="tint2.jpeg")
```

**输出:**
![](img/c4b42f896b0c5e3512a668cfa5f96ff7.png)