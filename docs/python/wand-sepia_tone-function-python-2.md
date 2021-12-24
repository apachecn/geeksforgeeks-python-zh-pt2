# 魔杖棕褐色 _tone()功能–Python

> 原文:[https://www . geesforgeks . org/wand-sepia _ tone-function-python-2/](https://www.geeksforgeeks.org/wand-sepia_tone-function-python-2/)

**棕褐色 _tone()** 模拟老式银基化学摄影印刷。sepia_tone()函数将 sepia 调色应用于图像。

> **语法:**
> 
> ```py
> wand.image.sepia_tone(threshold)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 阈值 | 数字。真实的 | 调色的程度。值可以在 0 & quantum_range 或 0 & 1.0 之间。默认值为 0.8 或“80%”。 |

**来源影像:**
![](img/a1d5dabac07efe8de363e0c440a198d8.png)

**例 1:**

```py
# Import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="koala.jpeg") as img:

    # Sepia simulation using sepia_tone() function
    img.sepia_tone(threshold = 0.6)
    img.save(filename ="sepiakoala2.jpeg")
```

**输出:**
![](img/2342f2f16022d6aac8a4d0b444171b8c.png)

**例 2:** 增加阈值。

```py
# Import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="koala.jpeg") as img:
    # Sepia simulation using sepia_tone() function
    img.sepia_tone(threshold = 1)
    img.save(filename ="sepiakoala.jpeg")
```

**输出:**
![](img/177f24702d7bd91e85a1c7b13724305b.png)