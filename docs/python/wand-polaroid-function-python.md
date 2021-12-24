# 魔杖偏光片()功能–Python

> 原文:[https://www . geesforgeks . org/wand-宝丽来-function-python/](https://www.geeksforgeeks.org/wand-polaroid-function-python/)

**宝丽来()**是功能最简单的功能之一。它生成带有轻微阴影的白色边框图像，以创建宝丽来打印的特殊效果。

> **语法:**
> 
> ```
> wand.image.polaroid(angle, caption, font, method)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 角 | 数字。真实的 | 沿此角度应用阴影效果。 |
> | 标题 | 基绳 | 在照片边框的底部书写信息。 |
> | 字体 | 墙字体字体字体 | 指定字体样式。 |
> | 方法 | 基绳 | 插值方法。仅限 ImageMagick-7。 |

**来源影像:**
![](img/a1d5dabac07efe8de363e0c440a198d8.png)

**例 1:**

```
# Import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="koala.jpeg") as img:
    # Polaroid image using polaroid() function
    img.polaroid()
    img.save(filename ="polkoala.jpeg")
```

**输出:**
![](img/2f4a15a7427223451e477f9b0a262178.png)

**示例 2:**
为图像添加标题和角度

```
# Import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="koala.jpeg") as img:
    # Polaroid image using polaroid() function
    img.polaroid(angle = 1.0, caption ="Hi Koala")
    img.save(filename ="polkoala2.jpeg")
```

**输出:**
![](img/324786724b1be4ab5bc470625a7dff43.png)