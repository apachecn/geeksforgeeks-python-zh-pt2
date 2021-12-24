# 魔杖内爆()功能–Python

> 原文:[https://www . geesforgeks . org/wand-inter decd-function-python-2/](https://www.geeksforgeeks.org/wand-implode-function-python-2/)

**内爆()**生成一种扭曲的图像，在图像的中间会注意到拉扯效应。amount 参数控制向中心拉的像素范围。

> **语法:**
> 
> ```py
> wand.image.implode(amount, method)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 数量 | 数字。真实的 | 0.0 到 1.0 之间的标准化影响程度。/td>
>  |
> | 方法 | 基绳 | 哪种插值方法适用于受影响的像素。
>  |

**来源影像:**
![](img/a1d5dabac07efe8de363e0c440a198d8.png)

**例 1:**

```py
# Import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="koala.jpeg") as img:

    # imploded image using implode() function
    img.implode(amount = 0.35)
    img.save(filename ="impkoala.jpeg")
```

**输出:**
![](img/b03825bdb11d4a58d0a51506e37894c7.png)

**例 2:**
增加金额值

```py
# Import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="koala.jpeg") as img:
    # Charcoal fx using charcoal() function
    img.implode(amount = 0.5)
    img.save(filename ="impkoala2.jpeg")
```

**输出:**
![](img/3ae1710a52dcb1eca9668f64878d33f7.png)