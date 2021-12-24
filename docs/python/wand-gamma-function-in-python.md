# Python 中的 Wand gamma()函数

> 原文:[https://www . geesforgeks . org/wand-gamma-function in-python/](https://www.geeksforgeeks.org/wand-gamma-function-in-python/)

**gamma()** 允许我们调整图像的亮度。产生的像素被定义为 pixel^(1/gamma).伽玛的值通常在 0.8 & 2.3 范围之间，1.0 的值不会影响生成的图像。

**参数:**

| 参数 | 输入类型 | 描述 |
| --- | --- | --- |
| 调整值 | 数字。真实的 | 用于调整伽玛水平的值。 |
| 频道 | 基绳 | 应用伽马校正的可选通道。 |

**Example:**

**来源影像:**
![](img/1872ab3ef601f11fa50ef88fbc76742b.png)

```py
# Import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="koala.jpeg") as img:
    img.gamma(1.35)
    img.save(filename ="kl-gamma.jpeg")
```

**输出:**
![](img/98ab2b2073f6b9842332249d5a913aec.png)

**例 2:** 将调整 _ 值增加到 1.75。

```py
# Import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="koala.jpeg") as img:
    img.gamma(1.75)
    img.save(filename ="kl-gamma2.jpeg")
```

**输出:**
![](img/f83caa53ee740c9573e783f11080697c.png)