# Python–在魔杖中锐化()功能

> 原文:[https://www . geeksforgeeks . org/python-锐化-魔杖中的功能/](https://www.geeksforgeeks.org/python-sharpen-function-in-wand/)

**锐化()**功能用于将模糊的边缘增强为更清晰(锐利)的边缘。这是使用高斯函数实现的。半径值应始终小于标准偏差(σ)。锐化效果图像更加清晰和明确。

> **语法:**
> 
> ```py
> wand.image.sharpen(radius, sigma, channel)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 半径 | 数字。真实的 | 高斯孔径的大小。 |
> | 希腊字母表中第十八个字母 | 数字，真实的 | 高斯滤波器的标准偏差。 |
> | 频道 | 基绳 | 目标可选颜色通道。默认值为无 |

**来源影像:**
![](img/a1d5dabac07efe8de363e0c440a198d8.png)

**例 1:**

```py
# import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="koala.jpeg") as img:
    # generating sharp image using sharpen() function.
    img.sharpen(radius = 8, sigma = 4)
    img.save(filename ="sharpkoala.jpeg")
```

**输出:**
![](img/cd6d09af80410777b6a8fd9503da06e4.png)

**例 2:**
增加半径和标准差的值。

```py
# import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="koala.jpeg") as img:

    # generating sharp image using sharpen() function.
    img.sharpen(radius = 16, sigma = 8)
    img.save(filename ="sharpkoala.jpeg")
```

**输出:** ![](img/731c5433e6561ca78159d1406c8b140b.png)